[posts](https://who23.github.io/) [about](https://who23.github.io/about) 🌙

# Sockets In Your Shell

Dec 3rd, 2020

Something I learned recently and I thought was _amazing_ \- you can create
sockets straight from your shell! Well, assuming you use bash or zsh - from
some surface level digging, I couldn’t find anything for fish.

Here’s how it works:

## bash

Bash supports tcp and udp connections out of the box, and does so with an
imaginary device in `/dev`. Enter

    
    
    $ echo "text!" > /dev/$PROTO/$HOST/$PORT
    

And you’ll create a connection to `HOST:PORT`. `$PROTO` can be `tcp` or `udp`.
If the connection can’t be made, writing to/reading the file will fail.

Along with being easy to access from the terminal, it’s _very_ handy for
scripts, especially if you don’t have `nc`/`telnet`. For example, if a local
build of a web app runs on port 8000, you can check if it’s running with:

    
    
    #!/bin/bash
    if [ exec 1>/dev/null 2>/dev/null 3>/dev/tcp/localhost/4000 ] ; then
    	echo "server up!"
    else
    	echo "server down."
    fi
    

And then use that information somewhere else.

If you’re unfamiliar, `exec` is used here to create the file to write to (>),
with file descriptor 3 referring to it and thus the connection.

We can use `exec` to create a connection we can read _and_ write to with `<>`,
and create a super simple curl:

    
    
    #!/bin/bash
    exec 3<>/dev/tcp/"$1"/80
    echo -e "GET / HTTP/1.1\n" >&3
    cat <&3
    
    
    
    $ ./simplecurl www.google.com
    HTTP/1.1 200 OK
    Date: Thu, 03 Dec 2020 00:57:30 GMT
    Expires: -1
    ....
    <google website>
    

I’m sure you can see the power of being able to open sockets with bash alone.
Go play around with it!

## zsh

zsh has an external module you can load in order to use it’s socket
capabilities. It doesn’t support udp like bash, but it’s more powerful in a
few ways!

To load the module, put the following in your `.zshrc` or run it in your
shell:

    
    
    $ zmodload zsh/net/tcp
    

We now have access to the zsh networking builtin - `ztcp`!

`ztcp` allows creating connections, like bash, but also allows listening for
connections.

Straight from the zsh docs, we can create a connection between two machines
with `ztcp`:

    
    
    # host machine:
    ztcp -l 7128
    lfd=$REPLY
    ztcp -a $lfd
    talkfd=$REPLY
    
    # client machine
    ztcp HOST 7128
    talkfd=$REPLY
    

The `$REPLY` variable here is a file descriptor returned by the last `ztcp`
command, referring to the socket/connection it just created.

So, `talkfd` on both machines is a file descriptor for talking to the other:

    
    
    # host machine
    echo -e "hello!" >&$talkfd
    
    # client machine
    read -r line <&$talkfd; print -r - $line
    > hello!
    

Again, there’s a lot more you can do, especially with the ability to listen
for connections.

Hope this was as interesting to you as it was to me!

[github](https://github.com/Who23)

