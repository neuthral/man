[

Better Dev

](https://betterdev.blog/ "Better Dev")

Toggle Navigation

  * [Series](https://betterdev.blog/series/ "Series")
  * [About](https://betterdev.blog/about/ "About")
  * [Contact](https://betterdev.blog/contact/ "Contact")

# Minimal safe Bash script template

#### Published by [**Maciej
Radzikowski**](https://betterdev.blog/author/maciej-radzikowski/) on December
14, 2020December 14, 2020

Contents

  * Why scripting in Bash?
  * Bash script template
    * Choose Bash
    * Fail fast
    * Get the location
    * Try to clean up
    * Display helpful help
    * Print nice messages
    * Parse any parameters
  * Using the template
  * Portability
  * Further reading
  * Closing notes

Bash scripts. Almost anyone needs to write one sooner or later. Almost no one
says “yeah, I love writing them”. And that’s why almost everyone is putting
low attention while writing them.

I won’t try to make you a Bash expert (since I’m not a one either), but I will
show you a minimal template that will make your scripts safer. You don’t need
to thank me, your future self will thank you.

## Why scripting in Bash?

The best summary of Bash scripting appeared recently on my Twitter feed:

> The opposite of "it's like riding a bike" is "it's like programming in
> bash".  
>  
> A phrase which means that no matter how many times you do something, you
> will have to re-learn it every single time.
>
> — Jake Wharton (@JakeWharton) [December 2,
> 2020](https://twitter.com/JakeWharton/status/1334177665356587008?ref_src=twsrc%5Etfw)

But Bash has something in common with another widely beloved language. Just
like JavaScript, it won’t go away easily. While we can hope that Bash won’t
become the main language for literally everything, it’s always somewhere near.

Bash [inherited the shell throne](https://www.quora.com/Is-Bash-considered-
the-lingua-franca-of-shells/answer/Paul-Reiber) and can be found on almost
every Linux, including Docker images. And this is the environment in which
most of the backend runs. So if you need to script the server application
startup, a CI/CD step, or integration test run, Bash is there for you.

To glue few commands together, pass output from one to another, and just start
some executable, Bash is the easiest and most native solution. While it makes
perfect sense to write bigger, more complicated scripts in other languages,
you can’t expect to have Python, Ruby, fish, or whatever another interpreter
you believe is the best, available everywhere. And you probably should think
twice and then once more before adding it to some prod server, Docker image,
or CI environment.

Yet Bash is far from perfect. The syntax is a nightmare. Error handling is
difficult. There are landmines everywhere. And we have to deal with it.

## Bash script template

Without further ado, here it is.

    
    
    #!/usr/bin/env bash
    
    set -Eeuo pipefail
    trap cleanup SIGINT SIGTERM ERR EXIT
    
    script_dir=$(cd "$(dirname "${BASH_SOURCE[0]}")" &>/dev/null && pwd -P)
    
    usage() {
      cat <<EOF
    Usage: $(basename "${BASH_SOURCE[0]}") [-h] [-v] [-f] -p param_value arg1 [arg2...]
    
    Script description here.
    
    Available options:
    
    -h, --help      Print this help and exit
    -v, --verbose   Print script debug info
    -f, --flag      Some flag description
    -p, --param     Some param description
    EOF
      exit
    }
    
    cleanup() {
      trap - SIGINT SIGTERM ERR EXIT
      # script cleanup here
    }
    
    setup_colors() {
      if [[ -t 2 ]] && [[ -z "${NO_COLOR-}" ]] && [[ "${TERM-}" != "dumb" ]]; then
        NOFORMAT='\033[0m' RED='\033[0;31m' GREEN='\033[0;32m' ORANGE='\033[0;33m' BLUE='\033[0;34m' PURPLE='\033[0;35m' CYAN='\033[0;36m' YELLOW='\033[1;33m'
      else
        NOFORMAT='' RED='' GREEN='' ORANGE='' BLUE='' PURPLE='' CYAN='' YELLOW=''
      fi
    }
    
    msg() {
      echo >&2 -e "${1-}"
    }
    
    die() {
      local msg=$1
      local code=${2-1} # default exit status 1
      msg "$msg"
      exit "$code"
    }
    
    parse_params() {
      # default values of variables set from params
      flag=0
      param=''
    
      while :; do
        case "${1-}" in
        -h | --help) usage ;;
        -v | --verbose) set -x ;;
        --no-color) NO_COLOR=1 ;;
        -f | --flag) flag=1 ;; # example flag
        -p | --param) # example named parameter
          param="${2-}"
          shift
          ;;
        -?*) die "Unknown option: $1" ;;
        *) break ;;
        esac
        shift
      done
    
      args=("$@")
    
      # check required params and arguments
      [[ -z "${param-}" ]] && die "Missing required parameter: param"
      [[ ${#args[@]} -eq 0 ]] && die "Missing script arguments"
    
      return 0
    }
    
    parse_params "$@"
    setup_colors
    
    # script logic here
    
    msg "${RED}Read parameters:${NOFORMAT}"
    msg "- flag: ${flag}"
    msg "- param: ${param}"
    msg "- arguments: ${args[*]-}"

The idea was to not make it too long. I don’t want to scroll 500 lines to the
script logic. At the same time, I want some strong foundations for any script.
But Bash is not making this easy, lacking any form of dependencies management.

One solution would be to have a separate script with all the boilerplate and
utility functions and execute it at the beginning. The downside would be to
have to always attach this second file everywhere, losing the “simple Bash
script” idea along the way. So I decided to put in the template only what I
consider to be a minimum to keep it possible short.

Now let’s look at it in more detail.

### Choose Bash

    
    
    #!/usr/bin/env bash

Script traditionally starts with a shebang. For the [best
compatibility](https://stackoverflow.com/questions/21612980/why-is-usr-bin-
env-bash-superior-to-bin-bash), it references `/usr/bin/env`, not the
`/bin/bash` directly. Although, if you read comments in the linked
StackOverflow question, even this can fail sometimes.

### Fail fast

    
    
    set -Eeuo pipefail

The `set` command changes script execution options. For example, **normally
Bash does not care if some command failed** , returning a non-zero exit status
code. It just happily jumps to the next one. Now consider this little script:

    
    
    #!/usr/bin/env bash
    cp important_file ./backups/
    rm important_file

What will happen, if the `backups` directory does not exist? Exactly, you will
get an error message in the console, but before you will be able to react, the
file will be already removed by the second command.

For details on what options exactly `set -Eeuo pipefail` changes and how they
will protect you, I refer you to the [article I have in my bookmarks for a few
years
now](https://vaneyckt.io/posts/safer_bash_scripts_with_set_euxo_pipefail/).

Although you should know that there are some [arguments against setting those
options](https://www.reddit.com/r/commandline/comments/g1vsxk/the_first_two_statements_of_your_bash_script/fniifmk?utm_source=share&utm_medium=web2x&context=3).

### Get the location

    
    
    script_dir=$(cd "$(dirname "${BASH_SOURCE[0]}")" &>/dev/null && pwd -P)

This line [does its best](https://stackoverflow.com/a/246128/2512304) to
define the script’s location directory ~~, and then we`cd` to it. Why?~~

Often our scripts are operating on paths relative to the script location,
copying files and executing commands, assuming the script directory is also a
working directory. And it is, as long as we execute the script from its
directory.

But if, let’s say, our CI config executes script like this:

    
    
    /opt/ci/project/script.sh

then our script is operating not in project dir, but some completely different
workdir of our CI tool. We can fix it, by going to the directory before
executing the script:

    
    
    cd /opt/ci/project && ./script.sh

But it’s much nicer to solve this on the script side. So, if the script reads
some file or executes another program from the same directory, call it like
this:

    
    
    cat "$script_dir/my_file"

At the same time, the script does not change the workdir location. If the
script is executed from some other directory and the user provides a relative
path to some file, we will still be able to read it.

### Try to clean up

    
    
    trap cleanup SIGINT SIGTERM ERR EXIT
    
    cleanup() {
      trap - SIGINT SIGTERM ERR EXIT
      # script cleanup here
    }

Think about the `trap` like of a `finally` block for the script. At the end of
the script – normal, caused by an error or an external signal – the
`cleanup()` function will be executed. This is a place where you can, for
example, try to remove all temporary files created by the script.

Just remember that the `cleanup()` can be called not only at the end but as
well having the script done any part of the work. Not necessarily all the
resources you try to cleanup will exist.

### Display helpful help

    
    
    usage() {
      cat <<EOF
    Usage: $(basename "${BASH_SOURCE[0]}") [-h] [-v] [-f] -p param_value arg1 [arg2...]
    
    Script description here.
    
    ...
    EOF
      exit
    }

Having the `usage()` relatively close to the top of the script, it will act in
two ways:

  * to **display help** for someone who does not know all the options and does not want to go over the whole script to discover them,
  * as a **minimal documentation** when someone modifies the script (for example you, 2 weeks later, not even remembering writing it in the first place).

I don’t argue to document every function here. But a short, nice script usage
message is a required minimum.

### Print nice messages

    
    
    setup_colors() {
      if [[ -t 2 ]] && [[ -z "${NO_COLOR-}" ]] && [[ "${TERM-}" != "dumb" ]]; then
        NOFORMAT='\033[0m' RED='\033[0;31m' GREEN='\033[0;32m' ORANGE='\033[0;33m' BLUE='\033[0;34m' PURPLE='\033[0;35m' CYAN='\033[0;36m' YELLOW='\033[1;33m'
      else
        NOFORMAT='' RED='' GREEN='' ORANGE='' BLUE='' PURPLE='' CYAN='' YELLOW=''
      fi
    }
    
    msg() {
      echo >&2 -e "${1-}"
    }

Firstly, remove the `setup_colors()` function if you don’t want to use colors
in text anyway. I keep it because I know I would use colors more often if I
wouldn’t have to google codes for them every time.

Secondly, those **colors are meant to be used with the`msg()` function only**,
not with the `echo` command.

The **`msg()` function is meant to be used to print everything that is not a
script output**. This includes all logs and messages, not only the errors.
Citing the great [12 Factor CLI Apps](https://medium.com/@jdxcode/12-factor-
cli-apps-dd3c227a0e46) article:

> **In short: stdout is for output, stderr is for messaging.**
>
> [Jeff Dickey](https://jdxcode.com/), who [knows a
> little](https://github.com/oclif/oclif/graphs/contributors) about [building
> CLI apps](https://github.com/heroku/cli/graphs/contributors)

That’s why in most cases you shouldn’t use colors for `stdout` anyway.

Messages printed with `msg()` are sent to `stderr` stream and support special
sequences, like colors. And colors are disabled anyway if the `stderr` output
is not an interactive terminal or [one of the standard parameters](https://no-
color.org/) is passed.

Usage:

    
    
    msg "This is a ${RED}very important${NOFORMAT} message, but not a script output value!"

To check how it behaves when the `stderr` is not an interactive terminal, add
a line like above to the script. Then execute it redirecting `stderr` to
`stdout` and piping it to `cat`. Pipe operation makes the output no longer
being sent directly to the terminal, but to the next command, so the colors
should be disabled now.

    
    
    $ ./test.sh 2>&1 | cat
    This is a very important message, but not a script output value!

### Parse any parameters

    
    
    parse_params() {
      # default values of variables set from params
      flag=0
      param=''
    
      while :; do
        case "${1-}" in
        -h | --help) usage ;;
        -v | --verbose) set -x ;;
        --no-color) NO_COLOR=1 ;;
        -f | --flag) flag=1 ;; # example flag
        -p | --param) # example named parameter
          param="${2-}"
          shift
          ;;
        -?*) die "Unknown option: $1" ;;
        *) break ;;
        esac
        shift
      done
    
      args=("$@")
    
      # check required params and arguments
      [[ -z "${param-}" ]] && die "Missing required parameter: param"
      [[ ${#args[@]} -eq 0 ]] && die "Missing script arguments"
    
      return 0
    }

If there is anything that makes sense to parametrized in the script, I usually
do that. Even if the script is used only in a single place. It makes it easier
to copy and reuse it, which often happens sooner than later. Also, even if
something needs to be hardcoded, usually there is a better place for that on a
higher level than the Bash script.

There are [three main types of CLI parameters](https://betterdev.blog/command-
line-arguments-anatomy-explained/) – flags, named parameters, and positional
arguments. The `parse_params()` function supports them all.

The only one of the common parameter patterns, that is not handled here, is
[concatenated multiple single-letter flags](https://betterdev.blog/command-
line-arguments-anatomy-explained/#flags_and_named_arguments). To be able to
pass two flags as `-ab`, instead of `-a -b`, some additional code would be
needed.

The `while` loop is a manual way of parsing parameters. In every other
language you should use one of the [built-in
parsers](https://docs.python.org/3/library/argparse.html) or [available
libraries](https://yargs.js.org/), but, well, this is Bash.

An example flag (`-f`) and named parameter (`-p`) are in the template. Just
change or copy them to add other params. And do not forget to update the
`usage()` afterward.

The important thing here, usually missing when you just take the first google
result for Bash arguments parsing, is **throwing an error on an unknown
option**. The fact the script received an unknown option means the user wanted
it to do something that the script is unable to fulfill. So user expectations
and script behavior may be quite different. It’s better to prevent execution
altogether before something bad will happen.

There are two alternatives for parsing parameters in Bash. It’s `getopt` and
`getopts`. There are [arguments both for and
against](https://unix.stackexchange.com/questions/62950/getopt-getopts-or-
manual-parsing-what-to-use-when-i-want-to-support-both-shor) using them. I
found those tools not best, since by default `getopt` on macOS is [behaving
completely differently](https://stackoverflow.com/questions/11777695/why-the-
getopt-doesnt-work-well-in-my-mac-os), and `getopts` does not support long
parameters (like `--help`).

## Using the template

Just copy-paste it, like most of the code you find on the internet.

Well, actually, it was quite honest advice. With Bash, there is no universal
`npm install` equivalent.

After you copy it, you only need to change 4 things:

  * `usage()` text with script description
  * `cleanup()` content
  * parameters in `parse_params()` – leave the `--help` and `--no-color`, but replace the example ones: `-f` and `-p`
  * actual script logic

## Portability

I tested the template on MacOS (with default, archaic Bash 3.2) and several
Docker images: Debian, Ubuntu, CentOS, Amazon Linux, Fedora. It works.

Obviously, it won’t work on environments missing Bash, like Alpine Linux.
Alpine, as a minimalistic system, uses very lightweight ash (Almquist shell).

You could ask a question if it wouldn’t be better to use [Bourne
shell](https://en.wikipedia.org/wiki/Bourne_shell)-compatible script that will
work almost everywhere. The answer, at least in my case, is no. Bash is safer
and more powerful (yet still not easy to use), so I can accept the lack of
support for a few Linux distros that I rarely have to deal with.

## Further reading

When creating a CLI script, in Bash or any ~~better~~ other language, there
are some universal rules. Those resources will guide you on how to make your
small scripts and big CLI apps reliable:

  * [Command Line Interface Guidelines](https://clig.dev/)
  * [12 Factor CLI Apps](https://medium.com/@jdxcode/12-factor-cli-apps-dd3c227a0e46)
  * [Command line arguments anatomy explained with examples](https://betterdev.blog/command-line-arguments-anatomy-explained/)

## Closing notes

I’m not the first and not the last to create a Bash script template. One good
alternative is [this project](https://github.com/ralish/bash-script-template),
although a little bit too big for my everyday needs. After all, I try to keep
Bash scripts as small (and rare) as possible.

When writing Bash scripts, use the IDE that supports
[ShellCheck](https://github.com/koalaman/shellcheck) linter, like JetBrains
IDEs. It will prevent you from doing [a bunch of
things](https://github.com/koalaman/shellcheck/blob/master/README.md#user-
content-gallery-of-bad-code) that can backfire on you.

My Bash script template is also available as GitHub Gist (under [MIT
license](https://gist.github.com/m-radzikowski/d925ac457478db14c2146deadd0020cd)):

[__script-
template.sh](https://gist.github.com/m-radzikowski/53e0b39e9a59a1518990e76c2bff8038)

If you found any problems with the template, or you think something important
is missing – let me know in the comments.

**Update 2020-12-15**

After a lot of comments here, on
[Reddit](https://www.reddit.com/r/programming/duplicates/kcxnag/minimal_safe_bash_script_template/),
and [HackerNews](https://news.ycombinator.com/item?id=25428621), I did some
improvements to the template. See revisions history in
[gist](https://gist.github.com/m-radzikowski/53e0b39e9a59a1518990e76c2bff8038).

**Update 2020-12-16**

Link to this post reached the [front page of Hacker News
(#7)](https://news.ycombinator.com/front?day=2020-12-15). This was completely
unexpected.

**Did you like this article? Join the free newsletter and never miss new
valuable content.**

Notice: JavaScript is required for this content.

Categories: [Programming](https://betterdev.blog/category/programming/)

Tags:
[bash](https://betterdev.blog/tag/bash/)[cli](https://betterdev.blog/tag/cli/)[level:beginner](https://betterdev.blog/tag/beginner/)[shell](https://betterdev.blog/tag/shell/)

[
__](https://www.facebook.com/sharer/sharer.php?u=https://betterdev.blog/minimal-
safe-bash-script-template/ "Share on Facebook") [
__](https://twitter.com/intent/tweet?url=https://betterdev.blog/minimal-safe-
bash-script-template/&text=Minimal%20safe%20Bash%20script%20template "Share on
Twitter") [
__](https://www.linkedin.com/shareArticle?mini=true&url=https://betterdev.blog/minimal-
safe-bash-script-template/&title=Minimal%20safe%20Bash%20script%20template
"Share on LinkedIn") [
__](https://reddit.com/submit?url=https://betterdev.blog/minimal-safe-bash-
script-template/&title=Minimal%20safe%20Bash%20script%20template "Share on
Reddit") [
__](mailto:?subject=Minimal%20safe%20Bash%20script%20template&body=https://betterdev.blog/minimal-
safe-bash-script-template/ "Send by email")

* * *

__ Subscribe __

Notify of

new follow-up comments new replies to my comments

I allow to use my email address and send notification about new comments and
replies (you can unsubscribe at any time).

![guest](data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD//gA7Q1JFQVRPUjogZ2QtanBlZyB2MS4wICh1c2luZyBJSkcgSlBFRyB2NjIpLCBxdWFsaXR5ID0gOTAK/9sAQwADAgIDAgIDAwMDBAMDBAUIBQUEBAUKBwcGCAwKDAwLCgsLDQ4SEA0OEQ4LCxAWEBETFBUVFQwPFxgWFBgSFBUU/9sAQwEDBAQFBAUJBQUJFA0LDRQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQU/8AAEQgAOAA4AwEiAAIRAQMRAf/EAB8AAAEFAQEBAQEBAAAAAAAAAAABAgMEBQYHCAkKC//EALUQAAIBAwMCBAMFBQQEAAABfQECAwAEEQUSITFBBhNRYQcicRQygZGhCCNCscEVUtHwJDNicoIJChYXGBkaJSYnKCkqNDU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6g4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2drh4uPk5ebn6Onq8fLz9PX29/j5+v/EAB8BAAMBAQEBAQEBAQEAAAAAAAABAgMEBQYHCAkKC//EALURAAIBAgQEAwQHBQQEAAECdwABAgMRBAUhMQYSQVEHYXETIjKBCBRCkaGxwQkjM1LwFWJy0QoWJDThJfEXGBkaJicoKSo1Njc4OTpDREVGR0hJSlNUVVZXWFlaY2RlZmdoaWpzdHV2d3h5eoKDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uLj5OXm5+jp6vLz9PX29/j5+v/aAAwDAQACEQMRAD8A+t80Zo4o4oAM0ZrsPBvw7m8Sxi7uZDa2GcKwHzyeu30HvXdf8Kp0Dytnlz7v+ennHP8Ah+lAHiuaM12XjL4dTeG4jd2sjXViDhiR88f1x1HvXG8UAGaKOKKADI9Kkt4vtFxFEOC7Bc/U4qPJ9KVXZGDLwwOQaAPpS0tY7G1ht4VCRRKEVcdABipc1meG9eh8RaRBeRMNzACRB1R+4/z2rU/OgCK5t47y3lgmUPFKpR1I6gjBr5uu4fst1NCefLdkz64OK+g/EWuQ+HtJnvJmHyjCIerv2Ar55klaWRnblmJJPqaAG5HpRRk+lFABzVnTtOutWvY7W0iMs8hwqj+Z9BVbB9a9o+GXhlNI0VL2VR9rvFD5PVY/4R+PX8vSgCfwX4EXwsDNJdSTXTrh1RisQ/Dv9T+QrrP89aT8qPyoA5Txr4FHilRNHdSQ3Ua4RHYtEfw7fUfrXjOo6dc6Tey2t3EYp4zgqf5j1FfSP5VxvxN8Mpq+jPfRKPtlmpfI6tH/ABD8Ov5+tAHi/NFGDRQBY060+3aja22f9dKsf5kD+tfSKIsaKigKqjAAHAFFFAC/j+lL+P6UUUAH4/pTXRZEZGG5WGCCOooooA+btRtPsOoXVtn/AFMrR/kSKKKKAP/Z)

{}

__

Name*

__

Email*

__Email address will not be publicly visible

__

Website

I agree to the website [Privacy Policy](https://betterdev.blog/privacy-
policy/)

____

![guest](data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD//gA7Q1JFQVRPUjogZ2QtanBlZyB2MS4wICh1c2luZyBJSkcgSlBFRyB2NjIpLCBxdWFsaXR5ID0gOTAK/9sAQwADAgIDAgIDAwMDBAMDBAUIBQUEBAUKBwcGCAwKDAwLCgsLDQ4SEA0OEQ4LCxAWEBETFBUVFQwPFxgWFBgSFBUU/9sAQwEDBAQFBAUJBQUJFA0LDRQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQU/8AAEQgAOAA4AwEiAAIRAQMRAf/EAB8AAAEFAQEBAQEBAAAAAAAAAAABAgMEBQYHCAkKC//EALUQAAIBAwMCBAMFBQQEAAABfQECAwAEEQUSITFBBhNRYQcicRQygZGhCCNCscEVUtHwJDNicoIJChYXGBkaJSYnKCkqNDU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6g4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2drh4uPk5ebn6Onq8fLz9PX29/j5+v/EAB8BAAMBAQEBAQEBAQEAAAAAAAABAgMEBQYHCAkKC//EALURAAIBAgQEAwQHBQQEAAECdwABAgMRBAUhMQYSQVEHYXETIjKBCBRCkaGxwQkjM1LwFWJy0QoWJDThJfEXGBkaJicoKSo1Njc4OTpDREVGR0hJSlNUVVZXWFlaY2RlZmdoaWpzdHV2d3h5eoKDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uLj5OXm5+jp6vLz9PX29/j5+v/aAAwDAQACEQMRAD8A+t80Zo4o4oAM0ZrsPBvw7m8Sxi7uZDa2GcKwHzyeu30HvXdf8Kp0Dytnlz7v+ennHP8Ah+lAHiuaM12XjL4dTeG4jd2sjXViDhiR88f1x1HvXG8UAGaKOKKADI9Kkt4vtFxFEOC7Bc/U4qPJ9KVXZGDLwwOQaAPpS0tY7G1ht4VCRRKEVcdABipc1meG9eh8RaRBeRMNzACRB1R+4/z2rU/OgCK5t47y3lgmUPFKpR1I6gjBr5uu4fst1NCefLdkz64OK+g/EWuQ+HtJnvJmHyjCIerv2Ar55klaWRnblmJJPqaAG5HpRRk+lFABzVnTtOutWvY7W0iMs8hwqj+Z9BVbB9a9o+GXhlNI0VL2VR9rvFD5PVY/4R+PX8vSgCfwX4EXwsDNJdSTXTrh1RisQ/Dv9T+QrrP89aT8qPyoA5Txr4FHilRNHdSQ3Ua4RHYtEfw7fUfrXjOo6dc6Tey2t3EYp4zgqf5j1FfSP5VxvxN8Mpq+jPfRKPtlmpfI6tH/ABD8Ov5+tAHi/NFGDRQBY060+3aja22f9dKsf5kD+tfSKIsaKigKqjAAHAFFFAC/j+lL+P6UUUAH4/pTXRZEZGG5WGCCOooooA+btRtPsOoXVtn/AFMrR/kSKKKKAP/Z)

{}

__

Name*

__

Email*

__Email address will not be publicly visible

__

Website

I agree to the website [Privacy Policy](https://betterdev.blog/privacy-
policy/)

____

41 Comments

__

__

Oldest __

Newest Most Voted

__Inline Feedbacks

View all comments

![Aurélien
Gâteau](data:image/png;base64,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)

[Aurélien Gâteau](http://agateau.com)

__19 days ago

__

Nice template!  
One thing though: cd-ing to the script dir is going to break for any script
which accept relative paths as arguments. This can be avoided by wrapping the
`cd` call with a `pushd $PWD > /dev/null` and `popd > /dev/null`.

4

Reply

__

[![Maciej
Radzikowski](data:image/jpeg;base64,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)](https://betterdev.blog/author/maciej-
radzikowski/)

Author

[Maciej Radzikowski](https://betterdev.blog/author/maciej-radzikowski/)

__19 days ago

__

__Reply to   Aurélien Gâteau

Thank you! That’s a quite nice solution for relative paths, I didn’t know it.
Let me test it out and update the template 🙂

1

Reply

![Stephen
Rees](data:image/jpeg;base64,/9j/4AAQSkZJRgABAQEAYABgAAD//gA7Q1JFQVRPUjogZ2QtanBlZyB2MS4wICh1c2luZyBJSkcgSlBFRyB2NjIpLCBxdWFsaXR5ID0gOTAK/9sAQwADAgIDAgIDAwMDBAMDBAUIBQUEBAUKBwcGCAwKDAwLCgsLDQ4SEA0OEQ4LCxAWEBETFBUVFQwPFxgWFBgSFBUU/9sAQwEDBAQFBAUJBQUJFA0LDRQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQU/8AAEQgAQABAAwEiAAIRAQMRAf/EAB8AAAEFAQEBAQEBAAAAAAAAAAABAgMEBQYHCAkKC//EALUQAAIBAwMCBAMFBQQEAAABfQECAwAEEQUSITFBBhNRYQcicRQygZGhCCNCscEVUtHwJDNicoIJChYXGBkaJSYnKCkqNDU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6g4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2drh4uPk5ebn6Onq8fLz9PX29/j5+v/EAB8BAAMBAQEBAQEBAQEAAAAAAAABAgMEBQYHCAkKC//EALURAAIBAgQEAwQHBQQEAAECdwABAgMRBAUhMQYSQVEHYXETIjKBCBRCkaGxwQkjM1LwFWJy0QoWJDThJfEXGBkaJicoKSo1Njc4OTpDREVGR0hJSlNUVVZXWFlaY2RlZmdoaWpzdHV2d3h5eoKDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uLj5OXm5+jp6vLz9PX29/j5+v/aAAwDAQACEQMRAD8A+uKKKKACipba1lvbiOCCNpZpDtVEGSTXe6X8Hry4iV769jtGIz5caeYR9TkD8s0Aee0V6Hqfwdu4ImexvUumHPlyJ5ZP0OSPzxXA3VpNY3EkFxE0M0ZwyOMEGgCKiiigAooooA9a+Enh+ODTX1aRA087FImP8KA4OPqQfyr0GuW+Glylx4OslQjdEXjcDsdxP8iD+NdTQAVwHxZ8Px3OlLqsaAXFuQsjAfeQnHP0JH5mu/rmfiPcpbeDr/eRmTbGo9SWH9AT+FAHhVFFFABRRVrS9MuNZv4bO1TzJpTgDsPUn2FAHQ+APGD+Gr8wyI81lcEB0QZZW7MB39x3/CvbYpBNGrrkKwBG5Sp/EHkVg+FfBdj4Xt1KIJ7wj57lhz9F9BXQ0ANkkEUbO2dqjJ2gk/kOTXifxA8Yv4kvVt4keGyt2O1HGGZuhYjt7D/Gvbq57xV4LsfFFuxdBBeAfJcqOfo3qKAPBaKtapplxo1/NZ3SeXNEcEdj6EexqrQAV678JvD62elvqki/v7klYyf4Ywf6kfoK8ir6P0ezGn6TZ2yjAhhRPyAoAuUUUUAFFFFAHA/Fnw+t5paapGv7+2IWQj+KMn+hP6mvIq+j9YsxqGk3lswyJoXT8wa+cKAP/9k=)

Stephen Rees

__18 days ago

__

__Reply to   Aurélien Gâteau

In a similar vein, I was thinking it would be polite to return the user to the
directory they were in prior to running the script, and the push and pop would
be useful for that.

0

Reply

__

![John
Kugelman](data:image/jpeg;base64,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)

John Kugelman

__18 days ago

__

__Reply to   Stephen Rees

No worries there. Scripts can’t change the working directory of the parent
shell.

1

Reply

![Arne](data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD//gA7Q1JFQVRPUjogZ2QtanBlZyB2MS4wICh1c2luZyBJSkcgSlBFRyB2NjIpLCBxdWFsaXR5ID0gOTAK/9sAQwADAgIDAgIDAwMDBAMDBAUIBQUEBAUKBwcGCAwKDAwLCgsLDQ4SEA0OEQ4LCxAWEBETFBUVFQwPFxgWFBgSFBUU/9sAQwEDBAQFBAUJBQUJFA0LDRQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQU/8AAEQgAQABAAwEiAAIRAQMRAf/EAB8AAAEFAQEBAQEBAAAAAAAAAAABAgMEBQYHCAkKC//EALUQAAIBAwMCBAMFBQQEAAABfQECAwAEEQUSITFBBhNRYQcicRQygZGhCCNCscEVUtHwJDNicoIJChYXGBkaJSYnKCkqNDU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6g4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2drh4uPk5ebn6Onq8fLz9PX29/j5+v/EAB8BAAMBAQEBAQEBAQEAAAAAAAABAgMEBQYHCAkKC//EALURAAIBAgQEAwQHBQQEAAECdwABAgMRBAUhMQYSQVEHYXETIjKBCBRCkaGxwQkjM1LwFWJy0QoWJDThJfEXGBkaJicoKSo1Njc4OTpDREVGR0hJSlNUVVZXWFlaY2RlZmdoaWpzdHV2d3h5eoKDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uLj5OXm5+jp6vLz9PX29/j5+v/aAAwDAQACEQMRAD8A+uKKKKACipba1lvbiOCCNpZpDtVEGSTXe6X8Hry4iV769jtGIz5caeYR9TkD8s0Aee0V6Hqfwdu4ImexvUumHPlyJ5ZP0OSPzxXA3VpNY3EkFxE0M0ZwyOMEGgCKiiigAooooA9a+Enh+ODTX1aRA087FImP8KA4OPqQfyr0GuW+Glylx4OslQjdEXjcDsdxP8iD+NdTQAVwHxZ8Px3OlLqsaAXFuQsjAfeQnHP0JH5mu/rmfiPcpbeDr/eRmTbGo9SWH9AT+FAHhVFFFABRRVrS9MuNZv4bO1TzJpTgDsPUn2FAHQ+APGD+Gr8wyI81lcEB0QZZW7MB39x3/CvbYpBNGrrkKwBG5Sp/EHkVg+FfBdj4Xt1KIJ7wj57lhz9F9BXQ0ANkkEUbO2dqjJ2gk/kOTXifxA8Yv4kvVt4keGyt2O1HGGZuhYjt7D/Gvbq57xV4LsfFFuxdBBeAfJcqOfo3qKAPBaKtapplxo1/NZ3SeXNEcEdj6EexqrQAV678JvD62elvqki/v7klYyf4Ywf6kfoK8ir6P0ezGn6TZ2yjAhhRPyAoAuUUUUAFFFFAHA/Fnw+t5paapGv7+2IWQj+KMn+hP6mvIq+j9YsxqGk3lswyJoXT8wa+cKAP/9k=)

Arne

__11 days ago

__

__Reply to   Aurélien Gâteau

You can also avoid `cd`-ing altogether using `realpath`.

    
    
    script_dir=$(realpath "$(dirname "${BASH_SOURCE[0]}")")
    

1

Reply

![John
Kugelman](data:image/jpeg;base64,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)

John Kugelman

__19 days ago

__

You can avoid the “scroll all the way to the bottom” problem by adding a
`main()` function. This lets you put the main script logic near the top and
keeps the logical flow top-to-bottom.

    
    
    main() {
      # script logic
    }
    
    ...
    
    # bottom of file
    main "$@"
    

I do this in all of my scripts.

6

Reply

__

![Peter
Forret](data:image/jpeg;base64,/9j/4AAQSkZJRgABAQEAYABgAAD//gA7Q1JFQVRPUjogZ2QtanBlZyB2MS4wICh1c2luZyBJSkcgSlBFRyB2NjIpLCBxdWFsaXR5ID0gOTAK/9sAQwADAgIDAgIDAwMDBAMDBAUIBQUEBAUKBwcGCAwKDAwLCgsLDQ4SEA0OEQ4LCxAWEBETFBUVFQwPFxgWFBgSFBUU/9sAQwEDBAQFBAUJBQUJFA0LDRQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQU/8AAEQgAQABAAwEiAAIRAQMRAf/EAB8AAAEFAQEBAQEBAAAAAAAAAAABAgMEBQYHCAkKC//EALUQAAIBAwMCBAMFBQQEAAABfQECAwAEEQUSITFBBhNRYQcicRQygZGhCCNCscEVUtHwJDNicoIJChYXGBkaJSYnKCkqNDU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6g4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2drh4uPk5ebn6Onq8fLz9PX29/j5+v/EAB8BAAMBAQEBAQEBAQEAAAAAAAABAgMEBQYHCAkKC//EALURAAIBAgQEAwQHBQQEAAECdwABAgMRBAUhMQYSQVEHYXETIjKBCBRCkaGxwQkjM1LwFWJy0QoWJDThJfEXGBkaJicoKSo1Njc4OTpDREVGR0hJSlNUVVZXWFlaY2RlZmdoaWpzdHV2d3h5eoKDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uLj5OXm5+jp6vLz9PX29/j5+v/aAAwDAQACEQMRAD8A+afjLpH9t+Ob/wAR2l4r28k/lxWowGiwADwOnINfQf7M/wAZNR0XdperSra25tSsdw8YBPtkjFec+BfAUev26akksU9zId7qzDJY89K9/wDA/gv/AIRNpNQ1K0jaJouFVTtU9934V+TvA4pYOEcPJNxVl3S/4B+E/wBqyxOKWjSj9rofNPxJ8Maxdatq+sTRy3VlLdNtuHXacE8ccV2Xw28J+JL/AE1jbG4aBVG4yAsq+2cHBr628A/DnT/jfFftqFuq+GtP2Gbyz80pGcID24HJHSuo1DVfBaxyaRbapouj6Vp5aEwLdxRCHaxUlwSCuWBAz1x15r6PJsoxPIqqqcqWmi10+5HrUchWZ071pe43p5/f+Z49pXi7SPB3h+wsrmJp71ysTRd930NeneAPFP8AZurxpDpatFdYURP8oz2PtXBfGLQrnwdIboQw6ppawtKEdQXVl7qexyR09e44rz/w14q1m41W3nikmjgkCyxvKmFwRlSG688V04zLXUfLiZKdOadvd6ruY5hKfDtWFLdaJWPqXxt4Ut49I1OxkgjtWvQ0m2I8Anvn14r5e+Nfwn1XV/hvealBAbp7YHy4oDltgI5I+gPFelQ/EfWZNTt7e+jF/NeYgjkaY4X065yKi8TeI9c+FHhnxFqk6trmmwx+c1ujDMfHIHtX8wY/C4rI86lDDRSvJSjFv4k3Z2fS/n6H0tHF0cfSnJbbPTbrqeeeG/gJZ6dbp9tvpNJaBA6hlMTOMcMAw5HQcV7nLFY+B/hzPqPi7QNQ8QW8bKEXT5duyDAG9tpDdSxPsOleW/EXxX418cw+EfEXifw/ZaboanyXbT7ku29hkO4xwp2ZAycd6+pfhV42svEHht103U4jcW8KSSGGNZcLgkgjIx0I7c1+/ZZmsK2Ohl8YaSV29Gnb/M48jyvDUcY+aN105r3kmr6p9uh+efjb9r/x34ZvNWsvhn4AfQ/AttctbLcXduJPMmC+YC02z77JFIQu4kr64zXlepfGT4q+LI/7S1fw5aHSdSIe7toCbee/jOM9DubI4ztII9RX6w/G6/Fh4E8QXVqyan4h0qx1C/0yAwiQw3YiYQsOPvqrNjv81fiG1tr/AIn1iS8aS9urnzw5nLZjWLuSe3f9MV+34CdoclNWW1lb/I9rMMLTouMXbRX1vbfZJNL/ACP0q+EnjSf4xfAOC8neBdVs0nguIHMfmrErsEJVOAdgXjA5B4qlFpeoafo1lpqiKa3igBeIf6yNQSEHvwMfVWHaue/Ys8EP4Z0C28W3E7iHxNBdmVJ8BA0ckaRhATzuVZJCSOd/evJviN8Xda0r9o7VtYspYobTT7OLS47dR+7mVZJHYuBjOS3PpkY6V8njlGdZ0qU7Wd/+AfXZfwpV4vjDB25aslo3tom9fJpWfY98jt49MVNV8l7iCDlYo/vI3rWHZ/Fe71i+1DT/AOxLifRruOTz2lAJVuQAQM8Y4rIsvj54V1fSWub2caPeSAg2a42uM4+Ulv5kVP8AD/xl4Q0+PV7rSddt9Sa4Ys22USbfYAV+ZZ9wvHNMdHE4m0YWSvfVO97r5nxmZ8IcQ8Hx5cTQag27yVpR6bvdJ6b29Tr/AIeaH4X1v4WWWkprmsXmrmfNvBcTyPHgv0VT8mApPI5z+VfP3hr9tS/+AfjrxN4d0H4errs82otFJdG6cTSRR7kjUIEI4BYknrkcDFfcH7OHh7w5oHgWy8VhfOdIDFZSyn5EQcM6D1JyuTz8p6Zr5m/bB+P2naC6QaZp1tGL262SCJVie4OCzMWXB4APOepFe5keVfUZ1MdioJTlZRV/hWu77u+vZI+myzIan1uhQxVo1I2jLTZ6Jt76rVOx7pofxl0OyjtL3V7mWa9vY1ZdPnlDTFyOQTnDMM7SQT26ivINf+DHw18W6zqGqW/hyaxa5kaeS3tLqWOIk8kFFYLg88Yr4Nufip53iCyuIDPBcLcxsJJJWLKQw5HJHH1r9PPg9psPj74e6D4uhTb/AGla7p4VPyLMrFJQB2AkRse1e9iK+JS/cOx+o57kWW4Jxnh6ntY3s79Huui3Xl0Pm/WfjnZaNoGseJpLY6cmkONI0nSEmLKXEcbxjbwNxLEsQOAAOcZr52fxBdam8t9qEglunUyykngnGazf2jvD3iDwP8ctesL2OXUIY7x57JSuFMDBSjDAA3KjIhbH8OD0rnLDX7XVIpF3kov+ujP3lA5Ix74xUqny2kne+r/yPsuC6lDBSqV5aVGrRT003um9+m2y9TrvC3h6HV4UE9rbTOP3lxfahJIApI6DaQcc/dH5VpT6n4e8OXrHRYkaZU2vNBujD+o27idvbB5+nbBtLe4mhL3DxBvviGdz5cXp8gIyfc4rmNf1nUkDLFfwoi/wwwgA/icn9aqpJOPJJJ37/wCR+jYmWGoYN+1ocyas7qLbVtb3a+e/mfV+gft1+G/Dvwo0rwnKuq+fp4kR51txsmBkZl2/N0AYDn0r5P8AiX441n9oP4jaba6Lp93dyyy/ZdP0+FC8ssjkDhR3PAx7V9nTf8EjPteuzR3Hxl0a30jzz5DwWBknMWeN6mZVDY9CRXuWh/Aj4RfsFWngnxfotyNc1WPX7aw1rXb6ZZJvst0kluxRQdsSJJLE52jcQmCzV0QrU21eWux/MmPx2Gr4meIprWUrvfdu/Uyf2U/+CY3hrwPYw6n8XLeLxL4nlhEqaU0paysCexA4lkHcnKg9AcBjN+wR4ik/4Qnxj4Gvn33/AIV1+e3KE8pFISw/8iJPX2/4g8XaBaqN+p2YkbgHz1/xr8w/Dnj7T/gX/wAFBfiLY3Op21r4d8S752uZJQIRJJtuY2z04Z5E9txrBYlTruhpZLp+pnhKtXGQr4e7lL3ZJel1ZL/t4k/4KJ/Cu/eNPGukIDNpyNBP/tW8mBuH+0r/AKH2r4f8PaFHCTAVIZQr3DKpJ9QpI6dq/Sb9rz4l+HPEPwZ1C30/WbG+mvJoEjW2uEc4DhmyATxhT+lfnnc6lE1y0b7EWUg4B5JAAGcdsCsJXpS5Htuv8j9Y4ZwfPg1icVupcqjLtZX9L6J+SJr7VLa3hKQyRwOAW+WHLf4n61wmr60s0zeXG7Z4zKckn2Hatq+mmhvZN7ebCrY8iTDceoPX9a5LxNq8UMhht0SFzxlRyoq6cfaS7ndn+ZSjSk5SUEna1t/TVr8n3P/Z)

[Peter Forret](https://blog.forret.com)

__18 days ago

__

__Reply to   John Kugelman

I had the same remark when I read this!  
I also have a bash template, a bit longer, with better option parsing and e.g.
automatic support for .env config files.  
<https://github.com/pforret/bashew>

0

Reply

[![Maciej
Radzikowski](data:image/jpeg;base64,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)](https://betterdev.blog/author/maciej-
radzikowski/)

Author

[Maciej Radzikowski](https://betterdev.blog/author/maciej-radzikowski/)

__18 days ago

__

__Reply to   John Kugelman

Fair point. But to have nice top-to-bottom overview of what’s happening in the
script, I would insist on having functions (from top):

  * usage
  * parse_params
  * main

This allows to read script and get to know what it does without jumping
around. First you read docs, then params, then main. So only thing to put
lower would be cleanup and messaging functions, which are not so long.  
But I agree that it is an improvement that can be applied here.

0

Reply

__

![Peter
Forret](data:image/jpeg;base64,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)

[Peter Forret](https://blog.forret.com)

__18 days ago

__

__Reply to   Maciej Radzikowski

I use a kind of CSV format for flags/options/parameters, and usage/option
initialisation/option parsing is automatically derived from that.  
Cf: <https://github.com/pforret/bashew/blob/master/template/normal.sh>

0

Reply

![Paul](data:image/jpeg;base64,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)

[Paul](https://dpaste.com)

__18 days ago

__

Thanks for sharing this, and for trying to raise the bar on Bash script
quality. We’ve all had “throwaway” scripts that didn’t get thrown away.

Since you were so conscientious about testing across OSs, allow me to suggest
you add FreeBSD to the list!

1

Reply

![Kirk
Bater](data:image/jpeg;base64,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)

[Kirk Bater](http://bater.io)

__18 days ago

__

I have a similar scaffold set up. I like your colors part, I’m probably going
to steal that 🙂  
With that said, one small usability improvement you could add is instead of
`break` ing on the arg parsing loop, push those into another var. By having
the break there instead of pushing to another var, you don’t allow your
scripts users to add flags after the positional args, which is annoying when
trying to debug why the script isn’t working by just adding `-v` to the end of
the command, you have to then put the flag towards the front of the command.
Example: in `myscript.sh -f --flag2 myarg1 myarg2 -v` the -v would be put into
the args variable instead of being parsed as a flag.  
So it would be something like this:

    
    
    args=()
    while :; do
        case "${1-}" in
        -h | --help)
          usage
          ;;
        *)
          args+=($1)
          ;;
        esac
        shift
      done
    

-1

Reply

![Petter](data:image/jpeg;base64,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)

Petter

__18 days ago

__

The template contains both NO_COLOR and NOCOLOR. They do different things.
This can be a bit confusing.

0

Reply

__

[![Maciej
Radzikowski](data:image/jpeg;base64,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)](https://betterdev.blog/author/maciej-
radzikowski/)

Author

[Maciej Radzikowski](https://betterdev.blog/author/maciej-radzikowski/)

__18 days ago

__

__Reply to   Petter

Good point, thank you. I will change the NOCOLOR to NOFORMAT, as it removes
also other formatting like bold etc.

0

Reply

![Savvas](data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD//gA7Q1JFQVRPUjogZ2QtanBlZyB2MS4wICh1c2luZyBJSkcgSlBFRyB2NjIpLCBxdWFsaXR5ID0gOTAK/9sAQwADAgIDAgIDAwMDBAMDBAUIBQUEBAUKBwcGCAwKDAwLCgsLDQ4SEA0OEQ4LCxAWEBETFBUVFQwPFxgWFBgSFBUU/9sAQwEDBAQFBAUJBQUJFA0LDRQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQU/8AAEQgAQABAAwEiAAIRAQMRAf/EAB8AAAEFAQEBAQEBAAAAAAAAAAABAgMEBQYHCAkKC//EALUQAAIBAwMCBAMFBQQEAAABfQECAwAEEQUSITFBBhNRYQcicRQygZGhCCNCscEVUtHwJDNicoIJChYXGBkaJSYnKCkqNDU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6g4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2drh4uPk5ebn6Onq8fLz9PX29/j5+v/EAB8BAAMBAQEBAQEBAQEAAAAAAAABAgMEBQYHCAkKC//EALURAAIBAgQEAwQHBQQEAAECdwABAgMRBAUhMQYSQVEHYXETIjKBCBRCkaGxwQkjM1LwFWJy0QoWJDThJfEXGBkaJicoKSo1Njc4OTpDREVGR0hJSlNUVVZXWFlaY2RlZmdoaWpzdHV2d3h5eoKDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uLj5OXm5+jp6vLz9PX29/j5+v/aAAwDAQACEQMRAD8A+uKKKKACipba1lvbiOCCNpZpDtVEGSTXe6X8Hry4iV769jtGIz5caeYR9TkD8s0Aee0V6Hqfwdu4ImexvUumHPlyJ5ZP0OSPzxXA3VpNY3EkFxE0M0ZwyOMEGgCKiiigAooooA9a+Enh+ODTX1aRA087FImP8KA4OPqQfyr0GuW+Glylx4OslQjdEXjcDsdxP8iD+NdTQAVwHxZ8Px3OlLqsaAXFuQsjAfeQnHP0JH5mu/rmfiPcpbeDr/eRmTbGo9SWH9AT+FAHhVFFFABRRVrS9MuNZv4bO1TzJpTgDsPUn2FAHQ+APGD+Gr8wyI81lcEB0QZZW7MB39x3/CvbYpBNGrrkKwBG5Sp/EHkVg+FfBdj4Xt1KIJ7wj57lhz9F9BXQ0ANkkEUbO2dqjJ2gk/kOTXifxA8Yv4kvVt4keGyt2O1HGGZuhYjt7D/Gvbq57xV4LsfFFuxdBBeAfJcqOfo3qKAPBaKtapplxo1/NZ3SeXNEcEdj6EexqrQAV678JvD62elvqki/v7klYyf4Ywf6kfoK8ir6P0ezGn6TZ2yjAhhRPyAoAuUUUUAFFFFAHA/Fnw+t5paapGv7+2IWQj+KMn+hP6mvIq+j9YsxqGk3lswyJoXT8wa+cKAP/9k=)

Savvas

__18 days ago

__

The pipefail is good, but has a bad side effect. If the originating command
does not produce any output, the pipefail will consider is as a failed one.
Case in point, when checking for files, according to same pattern and want to
count them or even the output of the pipe would be used elsewhere. If none,
the pipefail will it considered it failed.  
I did also some kind of templating, and the approach I used is to have all
these code in one file, and included in the other scripts. In fact, in order
to make it easier, instead of loading again and again the same code, I use a
code like this.  
I have a funcion in my template code, name exit_code. If that does not exist,
then try to find that library (named load.functions in my case) in the path
and home directory (you may add whaever you like) and then include it with the
source command (or mostly known as , )

    
    
    if [[ type -t exit_code"" != 'funtion' ]]; then
      DIR="$HOME $(echo $PATH | tr ':' ' ' )"
      mylib=$(find "${DIR}" -type f -name load.functions -printf '%T@ %p\n' 2>/dev/null | sort -n | tail -1 | cut -f2- --delimiter=' ')
      [[ -z ${mylib} || ! -f ${mylib} ]] && { echo "cannot load functions. abort"; exit 1; }
      source "${mylib}"
    else
      echo "cannot load functions. abort"
      exit 1
    fi
    

0

Reply

__

[![Maciej
Radzikowski](data:image/jpeg;base64,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)](https://betterdev.blog/author/maciej-
radzikowski/)

Author

[Maciej Radzikowski](https://betterdev.blog/author/maciej-radzikowski/)

__18 days ago

__

__Reply to   Savvas

Hey, this approach with separate files and even auto-loading is nice. The
drawback it’s only for own workstation. My goal here is to have something
relatively small that will work in all kind of environments.

1

Reply

__

![Savvas](data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD//gA7Q1JFQVRPUjogZ2QtanBlZyB2MS4wICh1c2luZyBJSkcgSlBFRyB2NjIpLCBxdWFsaXR5ID0gOTAK/9sAQwADAgIDAgIDAwMDBAMDBAUIBQUEBAUKBwcGCAwKDAwLCgsLDQ4SEA0OEQ4LCxAWEBETFBUVFQwPFxgWFBgSFBUU/9sAQwEDBAQFBAUJBQUJFA0LDRQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQU/8AAEQgAQABAAwEiAAIRAQMRAf/EAB8AAAEFAQEBAQEBAAAAAAAAAAABAgMEBQYHCAkKC//EALUQAAIBAwMCBAMFBQQEAAABfQECAwAEEQUSITFBBhNRYQcicRQygZGhCCNCscEVUtHwJDNicoIJChYXGBkaJSYnKCkqNDU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6g4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2drh4uPk5ebn6Onq8fLz9PX29/j5+v/EAB8BAAMBAQEBAQEBAQEAAAAAAAABAgMEBQYHCAkKC//EALURAAIBAgQEAwQHBQQEAAECdwABAgMRBAUhMQYSQVEHYXETIjKBCBRCkaGxwQkjM1LwFWJy0QoWJDThJfEXGBkaJicoKSo1Njc4OTpDREVGR0hJSlNUVVZXWFlaY2RlZmdoaWpzdHV2d3h5eoKDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uLj5OXm5+jp6vLz9PX29/j5+v/aAAwDAQACEQMRAD8A+uKKKKACipba1lvbiOCCNpZpDtVEGSTXe6X8Hry4iV769jtGIz5caeYR9TkD8s0Aee0V6Hqfwdu4ImexvUumHPlyJ5ZP0OSPzxXA3VpNY3EkFxE0M0ZwyOMEGgCKiiigAooooA9a+Enh+ODTX1aRA087FImP8KA4OPqQfyr0GuW+Glylx4OslQjdEXjcDsdxP8iD+NdTQAVwHxZ8Px3OlLqsaAXFuQsjAfeQnHP0JH5mu/rmfiPcpbeDr/eRmTbGo9SWH9AT+FAHhVFFFABRRVrS9MuNZv4bO1TzJpTgDsPUn2FAHQ+APGD+Gr8wyI81lcEB0QZZW7MB39x3/CvbYpBNGrrkKwBG5Sp/EHkVg+FfBdj4Xt1KIJ7wj57lhz9F9BXQ0ANkkEUbO2dqjJ2gk/kOTXifxA8Yv4kvVt4keGyt2O1HGGZuhYjt7D/Gvbq57xV4LsfFFuxdBBeAfJcqOfo3qKAPBaKtapplxo1/NZ3SeXNEcEdj6EexqrQAV678JvD62elvqki/v7klYyf4Ywf6kfoK8ir6P0ezGn6TZ2yjAhhRPyAoAuUUUUAFFFFAHA/Fnw+t5paapGv7+2IWQj+KMn+hP6mvIq+j9YsxqGk3lswyJoXT8wa+cKAP/9k=)

Savvas

__18 days ago

__

__Reply to   Maciej Radzikowski

except if you distribute the code, you distribute both files. But this makes
it easier to have real good and possibly several pages long, library code,
elsewhere, and not pollute the other scripts.

0

Reply

__

![Brian K.
White](data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD//gA7Q1JFQVRPUjogZ2QtanBlZyB2MS4wICh1c2luZyBJSkcgSlBFRyB2NjIpLCBxdWFsaXR5ID0gOTAK/9sAQwADAgIDAgIDAwMDBAMDBAUIBQUEBAUKBwcGCAwKDAwLCgsLDQ4SEA0OEQ4LCxAWEBETFBUVFQwPFxgWFBgSFBUU/9sAQwEDBAQFBAUJBQUJFA0LDRQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQU/8AAEQgAQABAAwEiAAIRAQMRAf/EAB8AAAEFAQEBAQEBAAAAAAAAAAABAgMEBQYHCAkKC//EALUQAAIBAwMCBAMFBQQEAAABfQECAwAEEQUSITFBBhNRYQcicRQygZGhCCNCscEVUtHwJDNicoIJChYXGBkaJSYnKCkqNDU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6g4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2drh4uPk5ebn6Onq8fLz9PX29/j5+v/EAB8BAAMBAQEBAQEBAQEAAAAAAAABAgMEBQYHCAkKC//EALURAAIBAgQEAwQHBQQEAAECdwABAgMRBAUhMQYSQVEHYXETIjKBCBRCkaGxwQkjM1LwFWJy0QoWJDThJfEXGBkaJicoKSo1Njc4OTpDREVGR0hJSlNUVVZXWFlaY2RlZmdoaWpzdHV2d3h5eoKDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uLj5OXm5+jp6vLz9PX29/j5+v/aAAwDAQACEQMRAD8A+uKKKKACipba1lvbiOCCNpZpDtVEGSTXe6X8Hry4iV769jtGIz5caeYR9TkD8s0Aee0V6Hqfwdu4ImexvUumHPlyJ5ZP0OSPzxXA3VpNY3EkFxE0M0ZwyOMEGgCKiiigAooooA9a+Enh+ODTX1aRA087FImP8KA4OPqQfyr0GuW+Glylx4OslQjdEXjcDsdxP8iD+NdTQAVwHxZ8Px3OlLqsaAXFuQsjAfeQnHP0JH5mu/rmfiPcpbeDr/eRmTbGo9SWH9AT+FAHhVFFFABRRVrS9MuNZv4bO1TzJpTgDsPUn2FAHQ+APGD+Gr8wyI81lcEB0QZZW7MB39x3/CvbYpBNGrrkKwBG5Sp/EHkVg+FfBdj4Xt1KIJ7wj57lhz9F9BXQ0ANkkEUbO2dqjJ2gk/kOTXifxA8Yv4kvVt4keGyt2O1HGGZuhYjt7D/Gvbq57xV4LsfFFuxdBBeAfJcqOfo3qKAPBaKtapplxo1/NZ3SeXNEcEdj6EexqrQAV678JvD62elvqki/v7klYyf4Ywf6kfoK8ir6P0ezGn6TZ2yjAhhRPyAoAuUUUUAFFFFAHA/Fnw+t5paapGv7+2IWQj+KMn+hP6mvIq+j9YsxqGk3lswyJoXT8wa+cKAP/9k=)

Brian K. White

__18 days ago

__

__Reply to   Savvas

He has an explicit design goal not to have multiple parts. It is a legit goal
for the stated reasons. Yes it’s a compromise. So is using Bash at all in the
first place.

Improvements that violate the design goal are not improvements, they are some
totally other answer to some totally other question.

1

Reply

![Benjamin
HENRION](data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD//gA7Q1JFQVRPUjogZ2QtanBlZyB2MS4wICh1c2luZyBJSkcgSlBFRyB2NjIpLCBxdWFsaXR5ID0gOTAK/9sAQwADAgIDAgIDAwMDBAMDBAUIBQUEBAUKBwcGCAwKDAwLCgsLDQ4SEA0OEQ4LCxAWEBETFBUVFQwPFxgWFBgSFBUU/9sAQwEDBAQFBAUJBQUJFA0LDRQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQU/8AAEQgAQABAAwEiAAIRAQMRAf/EAB8AAAEFAQEBAQEBAAAAAAAAAAABAgMEBQYHCAkKC//EALUQAAIBAwMCBAMFBQQEAAABfQECAwAEEQUSITFBBhNRYQcicRQygZGhCCNCscEVUtHwJDNicoIJChYXGBkaJSYnKCkqNDU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6g4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2drh4uPk5ebn6Onq8fLz9PX29/j5+v/EAB8BAAMBAQEBAQEBAQEAAAAAAAABAgMEBQYHCAkKC//EALURAAIBAgQEAwQHBQQEAAECdwABAgMRBAUhMQYSQVEHYXETIjKBCBRCkaGxwQkjM1LwFWJy0QoWJDThJfEXGBkaJicoKSo1Njc4OTpDREVGR0hJSlNUVVZXWFlaY2RlZmdoaWpzdHV2d3h5eoKDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uLj5OXm5+jp6vLz9PX29/j5+v/aAAwDAQACEQMRAD8A+uKKKKACipba1lvbiOCCNpZpDtVEGSTXe6X8Hry4iV769jtGIz5caeYR9TkD8s0Aee0V6Hqfwdu4ImexvUumHPlyJ5ZP0OSPzxXA3VpNY3EkFxE0M0ZwyOMEGgCKiiigAooooA9a+Enh+ODTX1aRA087FImP8KA4OPqQfyr0GuW+Glylx4OslQjdEXjcDsdxP8iD+NdTQAVwHxZ8Px3OlLqsaAXFuQsjAfeQnHP0JH5mu/rmfiPcpbeDr/eRmTbGo9SWH9AT+FAHhVFFFABRRVrS9MuNZv4bO1TzJpTgDsPUn2FAHQ+APGD+Gr8wyI81lcEB0QZZW7MB39x3/CvbYpBNGrrkKwBG5Sp/EHkVg+FfBdj4Xt1KIJ7wj57lhz9F9BXQ0ANkkEUbO2dqjJ2gk/kOTXifxA8Yv4kvVt4keGyt2O1HGGZuhYjt7D/Gvbq57xV4LsfFFuxdBBeAfJcqOfo3qKAPBaKtapplxo1/NZ3SeXNEcEdj6EexqrQAV678JvD62elvqki/v7klYyf4Ywf6kfoK8ir6P0ezGn6TZ2yjAhhRPyAoAuUUUUAFFFFAHA/Fnw+t5paapGv7+2IWQj+KMn+hP6mvIq+j9YsxqGk3lswyJoXT8wa+cKAP/9k=)

[Benjamin HENRION](http://www.zoobab.com)

__18 days ago

__

We should have a built-in bash library that simplifies a lot of functionality,
like:  
1\. check that a file exist, like check_file(filemane)  
2\. check that a directory exist, like check_dir(dirname)

-1

Reply

__

![Savvas](data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD//gA7Q1JFQVRPUjogZ2QtanBlZyB2MS4wICh1c2luZyBJSkcgSlBFRyB2NjIpLCBxdWFsaXR5ID0gOTAK/9sAQwADAgIDAgIDAwMDBAMDBAUIBQUEBAUKBwcGCAwKDAwLCgsLDQ4SEA0OEQ4LCxAWEBETFBUVFQwPFxgWFBgSFBUU/9sAQwEDBAQFBAUJBQUJFA0LDRQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQU/8AAEQgAQABAAwEiAAIRAQMRAf/EAB8AAAEFAQEBAQEBAAAAAAAAAAABAgMEBQYHCAkKC//EALUQAAIBAwMCBAMFBQQEAAABfQECAwAEEQUSITFBBhNRYQcicRQygZGhCCNCscEVUtHwJDNicoIJChYXGBkaJSYnKCkqNDU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6g4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2drh4uPk5ebn6Onq8fLz9PX29/j5+v/EAB8BAAMBAQEBAQEBAQEAAAAAAAABAgMEBQYHCAkKC//EALURAAIBAgQEAwQHBQQEAAECdwABAgMRBAUhMQYSQVEHYXETIjKBCBRCkaGxwQkjM1LwFWJy0QoWJDThJfEXGBkaJicoKSo1Njc4OTpDREVGR0hJSlNUVVZXWFlaY2RlZmdoaWpzdHV2d3h5eoKDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uLj5OXm5+jp6vLz9PX29/j5+v/aAAwDAQACEQMRAD8A+uKKKKACipba1lvbiOCCNpZpDtVEGSTXe6X8Hry4iV769jtGIz5caeYR9TkD8s0Aee0V6Hqfwdu4ImexvUumHPlyJ5ZP0OSPzxXA3VpNY3EkFxE0M0ZwyOMEGgCKiiigAooooA9a+Enh+ODTX1aRA087FImP8KA4OPqQfyr0GuW+Glylx4OslQjdEXjcDsdxP8iD+NdTQAVwHxZ8Px3OlLqsaAXFuQsjAfeQnHP0JH5mu/rmfiPcpbeDr/eRmTbGo9SWH9AT+FAHhVFFFABRRVrS9MuNZv4bO1TzJpTgDsPUn2FAHQ+APGD+Gr8wyI81lcEB0QZZW7MB39x3/CvbYpBNGrrkKwBG5Sp/EHkVg+FfBdj4Xt1KIJ7wj57lhz9F9BXQ0ANkkEUbO2dqjJ2gk/kOTXifxA8Yv4kvVt4keGyt2O1HGGZuhYjt7D/Gvbq57xV4LsfFFuxdBBeAfJcqOfo3qKAPBaKtapplxo1/NZ3SeXNEcEdj6EexqrQAV678JvD62elvqki/v7klYyf4Ywf6kfoK8ir6P0ezGn6TZ2yjAhhRPyAoAuUUUUAFFFFAHA/Fnw+t5paapGv7+2IWQj+KMn+hP6mvIq+j9YsxqGk3lswyJoXT8wa+cKAP/9k=)

Savvas

__18 days ago

__

__Reply to   Benjamin HENRION

[[ -f {filename} ]] && { code if true } || { code if false, file does not
exist}  
the same for directories, instead of -f, use -d.  
Why use a seperate function?

1

Reply

__

![Benjamin
HENRION](data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD//gA7Q1JFQVRPUjogZ2QtanBlZyB2MS4wICh1c2luZyBJSkcgSlBFRyB2NjIpLCBxdWFsaXR5ID0gOTAK/9sAQwADAgIDAgIDAwMDBAMDBAUIBQUEBAUKBwcGCAwKDAwLCgsLDQ4SEA0OEQ4LCxAWEBETFBUVFQwPFxgWFBgSFBUU/9sAQwEDBAQFBAUJBQUJFA0LDRQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQU/8AAEQgAQABAAwEiAAIRAQMRAf/EAB8AAAEFAQEBAQEBAAAAAAAAAAABAgMEBQYHCAkKC//EALUQAAIBAwMCBAMFBQQEAAABfQECAwAEEQUSITFBBhNRYQcicRQygZGhCCNCscEVUtHwJDNicoIJChYXGBkaJSYnKCkqNDU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6g4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2drh4uPk5ebn6Onq8fLz9PX29/j5+v/EAB8BAAMBAQEBAQEBAQEAAAAAAAABAgMEBQYHCAkKC//EALURAAIBAgQEAwQHBQQEAAECdwABAgMRBAUhMQYSQVEHYXETIjKBCBRCkaGxwQkjM1LwFWJy0QoWJDThJfEXGBkaJicoKSo1Njc4OTpDREVGR0hJSlNUVVZXWFlaY2RlZmdoaWpzdHV2d3h5eoKDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uLj5OXm5+jp6vLz9PX29/j5+v/aAAwDAQACEQMRAD8A+uKKKKACipba1lvbiOCCNpZpDtVEGSTXe6X8Hry4iV769jtGIz5caeYR9TkD8s0Aee0V6Hqfwdu4ImexvUumHPlyJ5ZP0OSPzxXA3VpNY3EkFxE0M0ZwyOMEGgCKiiigAooooA9a+Enh+ODTX1aRA087FImP8KA4OPqQfyr0GuW+Glylx4OslQjdEXjcDsdxP8iD+NdTQAVwHxZ8Px3OlLqsaAXFuQsjAfeQnHP0JH5mu/rmfiPcpbeDr/eRmTbGo9SWH9AT+FAHhVFFFABRRVrS9MuNZv4bO1TzJpTgDsPUn2FAHQ+APGD+Gr8wyI81lcEB0QZZW7MB39x3/CvbYpBNGrrkKwBG5Sp/EHkVg+FfBdj4Xt1KIJ7wj57lhz9F9BXQ0ANkkEUbO2dqjJ2gk/kOTXifxA8Yv4kvVt4keGyt2O1HGGZuhYjt7D/Gvbq57xV4LsfFFuxdBBeAfJcqOfo3qKAPBaKtapplxo1/NZ3SeXNEcEdj6EexqrQAV678JvD62elvqki/v7klYyf4Ywf6kfoK8ir6P0ezGn6TZ2yjAhhRPyAoAuUUUUAFFFFAHA/Fnw+t5paapGv7+2IWQj+KMn+hP6mvIq+j9YsxqGk3lswyJoXT8wa+cKAP/9k=)

[Benjamin HENRION](http://www.zoobab.com)

__18 days ago

__

__Reply to   Savvas

That was a bad example, because the solution was a onliner.  
Is there a good bash library with lots of useful functions?

0

Reply

__

![Peter
Forret](data:image/jpeg;base64,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)

[Peter Forret](https://blog.forret.com)

__18 days ago

__

__Reply to   Benjamin HENRION

Check out <https://github.com/pforret/bashew>  
It’s got option parsing, text output functions, hash, slugify,
lower/uppercase, folder cleanup, …

0

Reply

![Richard](data:image/jpeg;base64,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)

Richard

__18 days ago

__

Nice minimal template, thanks for posting it!  
I had the same thoughts expressed in several other comments: NO_COLOR vs.
NOCOLOR confusion, main() function wrapping, and quickly appending args on
subsequent runs (i.e., add trailing `-v`) all seem like good improvements.  
I would use `--debug` (and no `-d`) for `set -x`, which I think of as
debugging by the script **author** (`set -x` is rather low-level output to an
average user). I would use a `--verbose`

`-v` options for printing more task specific details to the script **user**. I
wouldn’t expose debugging with `-d` because such a common letter is likely to
be desired for a task specific option.

0

Reply

__

[![Maciej
Radzikowski](data:image/jpeg;base64,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)](https://betterdev.blog/author/maciej-
radzikowski/)

Author

[Maciej Radzikowski](https://betterdev.blog/author/maciej-radzikowski/)

__18 days ago

__

__Reply to   Richard

Thanks for the comment! I applied some changes and updated the template.  
With verbose and debug – I see your point and agree in the case of bigger
scripts and CLI apps. Here I hope no one will build a big CLI app based on
this template! I was thinking more about quite simple utility scripts that we
all create to get things working.

0

Reply

![Bruno
Paulino](data:image/jpeg;base64,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)

[Bruno Paulino](https://bpaulino.com)

__18 days ago

__

This is Gold! Thanks a lot for sharing this.

0

Reply

![Brian K.
White](data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD//gA7Q1JFQVRPUjogZ2QtanBlZyB2MS4wICh1c2luZyBJSkcgSlBFRyB2NjIpLCBxdWFsaXR5ID0gOTAK/9sAQwADAgIDAgIDAwMDBAMDBAUIBQUEBAUKBwcGCAwKDAwLCgsLDQ4SEA0OEQ4LCxAWEBETFBUVFQwPFxgWFBgSFBUU/9sAQwEDBAQFBAUJBQUJFA0LDRQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQU/8AAEQgAQABAAwEiAAIRAQMRAf/EAB8AAAEFAQEBAQEBAAAAAAAAAAABAgMEBQYHCAkKC//EALUQAAIBAwMCBAMFBQQEAAABfQECAwAEEQUSITFBBhNRYQcicRQygZGhCCNCscEVUtHwJDNicoIJChYXGBkaJSYnKCkqNDU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6g4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2drh4uPk5ebn6Onq8fLz9PX29/j5+v/EAB8BAAMBAQEBAQEBAQEAAAAAAAABAgMEBQYHCAkKC//EALURAAIBAgQEAwQHBQQEAAECdwABAgMRBAUhMQYSQVEHYXETIjKBCBRCkaGxwQkjM1LwFWJy0QoWJDThJfEXGBkaJicoKSo1Njc4OTpDREVGR0hJSlNUVVZXWFlaY2RlZmdoaWpzdHV2d3h5eoKDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uLj5OXm5+jp6vLz9PX29/j5+v/aAAwDAQACEQMRAD8A+uKKKKACipba1lvbiOCCNpZpDtVEGSTXe6X8Hry4iV769jtGIz5caeYR9TkD8s0Aee0V6Hqfwdu4ImexvUumHPlyJ5ZP0OSPzxXA3VpNY3EkFxE0M0ZwyOMEGgCKiiigAooooA9a+Enh+ODTX1aRA087FImP8KA4OPqQfyr0GuW+Glylx4OslQjdEXjcDsdxP8iD+NdTQAVwHxZ8Px3OlLqsaAXFuQsjAfeQnHP0JH5mu/rmfiPcpbeDr/eRmTbGo9SWH9AT+FAHhVFFFABRRVrS9MuNZv4bO1TzJpTgDsPUn2FAHQ+APGD+Gr8wyI81lcEB0QZZW7MB39x3/CvbYpBNGrrkKwBG5Sp/EHkVg+FfBdj4Xt1KIJ7wj57lhz9F9BXQ0ANkkEUbO2dqjJ2gk/kOTXifxA8Yv4kvVt4keGyt2O1HGGZuhYjt7D/Gvbq57xV4LsfFFuxdBBeAfJcqOfo3qKAPBaKtapplxo1/NZ3SeXNEcEdj6EexqrQAV678JvD62elvqki/v7klYyf4Ywf6kfoK8ir6P0ezGn6TZ2yjAhhRPyAoAuUUUUAFFFFAHA/Fnw+t5paapGv7+2IWQj+KMn+hP6mvIq+j9YsxqGk3lswyJoXT8wa+cKAP/9k=)

Brian K. White

__18 days ago

__

script_dir=${0%/*}

both basename and dirname are built-in in this way. This is just dirname.

For completeness, basename is ${0##*/}

-1

Reply

![Jon
Hell](data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD//gA7Q1JFQVRPUjogZ2QtanBlZyB2MS4wICh1c2luZyBJSkcgSlBFRyB2NjIpLCBxdWFsaXR5ID0gOTAK/9sAQwADAgIDAgIDAwMDBAMDBAUIBQUEBAUKBwcGCAwKDAwLCgsLDQ4SEA0OEQ4LCxAWEBETFBUVFQwPFxgWFBgSFBUU/9sAQwEDBAQFBAUJBQUJFA0LDRQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQU/8AAEQgAQABAAwEiAAIRAQMRAf/EAB8AAAEFAQEBAQEBAAAAAAAAAAABAgMEBQYHCAkKC//EALUQAAIBAwMCBAMFBQQEAAABfQECAwAEEQUSITFBBhNRYQcicRQygZGhCCNCscEVUtHwJDNicoIJChYXGBkaJSYnKCkqNDU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6g4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2drh4uPk5ebn6Onq8fLz9PX29/j5+v/EAB8BAAMBAQEBAQEBAQEAAAAAAAABAgMEBQYHCAkKC//EALURAAIBAgQEAwQHBQQEAAECdwABAgMRBAUhMQYSQVEHYXETIjKBCBRCkaGxwQkjM1LwFWJy0QoWJDThJfEXGBkaJicoKSo1Njc4OTpDREVGR0hJSlNUVVZXWFlaY2RlZmdoaWpzdHV2d3h5eoKDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uLj5OXm5+jp6vLz9PX29/j5+v/aAAwDAQACEQMRAD8A+uKKKKACipba1lvbiOCCNpZpDtVEGSTXe6X8Hry4iV769jtGIz5caeYR9TkD8s0Aee0V6Hqfwdu4ImexvUumHPlyJ5ZP0OSPzxXA3VpNY3EkFxE0M0ZwyOMEGgCKiiigAooooA9a+Enh+ODTX1aRA087FImP8KA4OPqQfyr0GuW+Glylx4OslQjdEXjcDsdxP8iD+NdTQAVwHxZ8Px3OlLqsaAXFuQsjAfeQnHP0JH5mu/rmfiPcpbeDr/eRmTbGo9SWH9AT+FAHhVFFFABRRVrS9MuNZv4bO1TzJpTgDsPUn2FAHQ+APGD+Gr8wyI81lcEB0QZZW7MB39x3/CvbYpBNGrrkKwBG5Sp/EHkVg+FfBdj4Xt1KIJ7wj57lhz9F9BXQ0ANkkEUbO2dqjJ2gk/kOTXifxA8Yv4kvVt4keGyt2O1HGGZuhYjt7D/Gvbq57xV4LsfFFuxdBBeAfJcqOfo3qKAPBaKtapplxo1/NZ3SeXNEcEdj6EexqrQAV678JvD62elvqki/v7klYyf4Ywf6kfoK8ir6P0ezGn6TZ2yjAhhRPyAoAuUUUUAFFFFAHA/Fnw+t5paapGv7+2IWQj+KMn+hP6mvIq+j9YsxqGk3lswyJoXT8wa+cKAP/9k=)

Jon Hell

__18 days ago

__

_getopts_ is also another way to handle the flags that are passed in a more
structured way. You can specify what flags are possible and flag arguments can
be separated by a space or directly after the flag. multiple flags can be
applied with one single “-” to get compounding options (ex. rm -rf)

I think that is the standard way of handling flags in more complex scripts

0

Reply

__

![Brian K.
White](data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD//gA7Q1JFQVRPUjogZ2QtanBlZyB2MS4wICh1c2luZyBJSkcgSlBFRyB2NjIpLCBxdWFsaXR5ID0gOTAK/9sAQwADAgIDAgIDAwMDBAMDBAUIBQUEBAUKBwcGCAwKDAwLCgsLDQ4SEA0OEQ4LCxAWEBETFBUVFQwPFxgWFBgSFBUU/9sAQwEDBAQFBAUJBQUJFA0LDRQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQU/8AAEQgAQABAAwEiAAIRAQMRAf/EAB8AAAEFAQEBAQEBAAAAAAAAAAABAgMEBQYHCAkKC//EALUQAAIBAwMCBAMFBQQEAAABfQECAwAEEQUSITFBBhNRYQcicRQygZGhCCNCscEVUtHwJDNicoIJChYXGBkaJSYnKCkqNDU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6g4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2drh4uPk5ebn6Onq8fLz9PX29/j5+v/EAB8BAAMBAQEBAQEBAQEAAAAAAAABAgMEBQYHCAkKC//EALURAAIBAgQEAwQHBQQEAAECdwABAgMRBAUhMQYSQVEHYXETIjKBCBRCkaGxwQkjM1LwFWJy0QoWJDThJfEXGBkaJicoKSo1Njc4OTpDREVGR0hJSlNUVVZXWFlaY2RlZmdoaWpzdHV2d3h5eoKDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uLj5OXm5+jp6vLz9PX29/j5+v/aAAwDAQACEQMRAD8A+uKKKKACipba1lvbiOCCNpZpDtVEGSTXe6X8Hry4iV769jtGIz5caeYR9TkD8s0Aee0V6Hqfwdu4ImexvUumHPlyJ5ZP0OSPzxXA3VpNY3EkFxE0M0ZwyOMEGgCKiiigAooooA9a+Enh+ODTX1aRA087FImP8KA4OPqQfyr0GuW+Glylx4OslQjdEXjcDsdxP8iD+NdTQAVwHxZ8Px3OlLqsaAXFuQsjAfeQnHP0JH5mu/rmfiPcpbeDr/eRmTbGo9SWH9AT+FAHhVFFFABRRVrS9MuNZv4bO1TzJpTgDsPUn2FAHQ+APGD+Gr8wyI81lcEB0QZZW7MB39x3/CvbYpBNGrrkKwBG5Sp/EHkVg+FfBdj4Xt1KIJ7wj57lhz9F9BXQ0ANkkEUbO2dqjJ2gk/kOTXifxA8Yv4kvVt4keGyt2O1HGGZuhYjt7D/Gvbq57xV4LsfFFuxdBBeAfJcqOfo3qKAPBaKtapplxo1/NZ3SeXNEcEdj6EexqrQAV678JvD62elvqki/v7klYyf4Ywf6kfoK8ir6P0ezGn6TZ2yjAhhRPyAoAuUUUUAFFFFAHA/Fnw+t5paapGv7+2IWQj+KMn+hP6mvIq+j9YsxqGk3lswyJoXT8wa+cKAP/9k=)

Brian K. White

__18 days ago

__

__Reply to   Jon Hell

The article addresses (and dismisses) both getopt and getopts.

1

Reply

![Dan
B](data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD//gA7Q1JFQVRPUjogZ2QtanBlZyB2MS4wICh1c2luZyBJSkcgSlBFRyB2NjIpLCBxdWFsaXR5ID0gOTAK/9sAQwADAgIDAgIDAwMDBAMDBAUIBQUEBAUKBwcGCAwKDAwLCgsLDQ4SEA0OEQ4LCxAWEBETFBUVFQwPFxgWFBgSFBUU/9sAQwEDBAQFBAUJBQUJFA0LDRQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQU/8AAEQgAQABAAwEiAAIRAQMRAf/EAB8AAAEFAQEBAQEBAAAAAAAAAAABAgMEBQYHCAkKC//EALUQAAIBAwMCBAMFBQQEAAABfQECAwAEEQUSITFBBhNRYQcicRQygZGhCCNCscEVUtHwJDNicoIJChYXGBkaJSYnKCkqNDU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6g4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2drh4uPk5ebn6Onq8fLz9PX29/j5+v/EAB8BAAMBAQEBAQEBAQEAAAAAAAABAgMEBQYHCAkKC//EALURAAIBAgQEAwQHBQQEAAECdwABAgMRBAUhMQYSQVEHYXETIjKBCBRCkaGxwQkjM1LwFWJy0QoWJDThJfEXGBkaJicoKSo1Njc4OTpDREVGR0hJSlNUVVZXWFlaY2RlZmdoaWpzdHV2d3h5eoKDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uLj5OXm5+jp6vLz9PX29/j5+v/aAAwDAQACEQMRAD8A+uKKKKACipba1lvbiOCCNpZpDtVEGSTXe6X8Hry4iV769jtGIz5caeYR9TkD8s0Aee0V6Hqfwdu4ImexvUumHPlyJ5ZP0OSPzxXA3VpNY3EkFxE0M0ZwyOMEGgCKiiigAooooA9a+Enh+ODTX1aRA087FImP8KA4OPqQfyr0GuW+Glylx4OslQjdEXjcDsdxP8iD+NdTQAVwHxZ8Px3OlLqsaAXFuQsjAfeQnHP0JH5mu/rmfiPcpbeDr/eRmTbGo9SWH9AT+FAHhVFFFABRRVrS9MuNZv4bO1TzJpTgDsPUn2FAHQ+APGD+Gr8wyI81lcEB0QZZW7MB39x3/CvbYpBNGrrkKwBG5Sp/EHkVg+FfBdj4Xt1KIJ7wj57lhz9F9BXQ0ANkkEUbO2dqjJ2gk/kOTXifxA8Yv4kvVt4keGyt2O1HGGZuhYjt7D/Gvbq57xV4LsfFFuxdBBeAfJcqOfo3qKAPBaKtapplxo1/NZ3SeXNEcEdj6EexqrQAV678JvD62elvqki/v7klYyf4Ywf6kfoK8ir6P0ezGn6TZ2yjAhhRPyAoAuUUUUAFFFFAHA/Fnw+t5paapGv7+2IWQj+KMn+hP6mvIq+j9YsxqGk3lswyJoXT8wa+cKAP/9k=)

[Dan B](http://swagg.net/)

__17 days ago

__

>What will happen, if the `backups` directory does not exist? Exactly, you
will get an error message in the console, but before you will be able to
react, the file will be already removed by the second command.

    
    
    if [ -d ./backups ]; then mv important_file ./backups/; fi
    

__Last edited 17 days ago by Dan B

0

Reply

__

[![Maciej
Radzikowski](data:image/jpeg;base64,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)](https://betterdev.blog/author/maciej-
radzikowski/)

Author

[Maciej Radzikowski](https://betterdev.blog/author/maciej-radzikowski/)

__16 days ago

__

__Reply to   Dan B

Sure. It was just a simple example that could be fixed in several ways. The
point is that every command can fail, and that can have more or less serious
consequences on how the rest of the script will behave.  
Handling possible failure of only the parts that can have an impact on the
next commands is all good until you miss one spot. That’s why I believe it’s
better to make Bash behave more like most other languages – something fails,
the process is stopped.

0

Reply

__

![Dan
B](data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD//gA7Q1JFQVRPUjogZ2QtanBlZyB2MS4wICh1c2luZyBJSkcgSlBFRyB2NjIpLCBxdWFsaXR5ID0gOTAK/9sAQwADAgIDAgIDAwMDBAMDBAUIBQUEBAUKBwcGCAwKDAwLCgsLDQ4SEA0OEQ4LCxAWEBETFBUVFQwPFxgWFBgSFBUU/9sAQwEDBAQFBAUJBQUJFA0LDRQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQU/8AAEQgAQABAAwEiAAIRAQMRAf/EAB8AAAEFAQEBAQEBAAAAAAAAAAABAgMEBQYHCAkKC//EALUQAAIBAwMCBAMFBQQEAAABfQECAwAEEQUSITFBBhNRYQcicRQygZGhCCNCscEVUtHwJDNicoIJChYXGBkaJSYnKCkqNDU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6g4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2drh4uPk5ebn6Onq8fLz9PX29/j5+v/EAB8BAAMBAQEBAQEBAQEAAAAAAAABAgMEBQYHCAkKC//EALURAAIBAgQEAwQHBQQEAAECdwABAgMRBAUhMQYSQVEHYXETIjKBCBRCkaGxwQkjM1LwFWJy0QoWJDThJfEXGBkaJicoKSo1Njc4OTpDREVGR0hJSlNUVVZXWFlaY2RlZmdoaWpzdHV2d3h5eoKDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uLj5OXm5+jp6vLz9PX29/j5+v/aAAwDAQACEQMRAD8A+uKKKKACipba1lvbiOCCNpZpDtVEGSTXe6X8Hry4iV769jtGIz5caeYR9TkD8s0Aee0V6Hqfwdu4ImexvUumHPlyJ5ZP0OSPzxXA3VpNY3EkFxE0M0ZwyOMEGgCKiiigAooooA9a+Enh+ODTX1aRA087FImP8KA4OPqQfyr0GuW+Glylx4OslQjdEXjcDsdxP8iD+NdTQAVwHxZ8Px3OlLqsaAXFuQsjAfeQnHP0JH5mu/rmfiPcpbeDr/eRmTbGo9SWH9AT+FAHhVFFFABRRVrS9MuNZv4bO1TzJpTgDsPUn2FAHQ+APGD+Gr8wyI81lcEB0QZZW7MB39x3/CvbYpBNGrrkKwBG5Sp/EHkVg+FfBdj4Xt1KIJ7wj57lhz9F9BXQ0ANkkEUbO2dqjJ2gk/kOTXifxA8Yv4kvVt4keGyt2O1HGGZuhYjt7D/Gvbq57xV4LsfFFuxdBBeAfJcqOfo3qKAPBaKtapplxo1/NZ3SeXNEcEdj6EexqrQAV678JvD62elvqki/v7klYyf4Ywf6kfoK8ir6P0ezGn6TZ2yjAhhRPyAoAuUUUUAFFFFAHA/Fnw+t5paapGv7+2IWQj+KMn+hP6mvIq+j9YsxqGk3lswyJoXT8wa+cKAP/9k=)

[Dan B](http://swagg.net/)

__15 days ago

__

__Reply to   Maciej Radzikowski

>That’s why I believe it’s better to make Bash behave more like most other
languages – something fails, the process is stopped.  
I disagree because I take that to be re-inventing the wheel. In most of the
shell scripts I’ve seen it’s very common to see things like:

    
    
    if [ -x /etc/rc.d/rc.httpd ]; then
        /etc/rc.d/rc.httpd start
    fi
    

I guess it sounds dismissive or unsexy to say “this is the convention, just
stick to this” but I mean it’s just worked and continues to work without
having to beat your shell script into submission to act like it’s written in a
more modern scripting language. That’s why IMO, shell scripts are great for
sys-admin type stuff like moving files around and setting up the environment
but it’s ok to reach for another scripting language when you want something
more portable and does fancier things. Shell scripts can also run Ruby one-
liners or other Python scripts too, you can use them as “wrappers” or “glue”
for these other things

0

Reply

![Bob
Smith](data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD//gA7Q1JFQVRPUjogZ2QtanBlZyB2MS4wICh1c2luZyBJSkcgSlBFRyB2NjIpLCBxdWFsaXR5ID0gOTAK/9sAQwADAgIDAgIDAwMDBAMDBAUIBQUEBAUKBwcGCAwKDAwLCgsLDQ4SEA0OEQ4LCxAWEBETFBUVFQwPFxgWFBgSFBUU/9sAQwEDBAQFBAUJBQUJFA0LDRQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQU/8AAEQgAQABAAwEiAAIRAQMRAf/EAB8AAAEFAQEBAQEBAAAAAAAAAAABAgMEBQYHCAkKC//EALUQAAIBAwMCBAMFBQQEAAABfQECAwAEEQUSITFBBhNRYQcicRQygZGhCCNCscEVUtHwJDNicoIJChYXGBkaJSYnKCkqNDU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6g4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2drh4uPk5ebn6Onq8fLz9PX29/j5+v/EAB8BAAMBAQEBAQEBAQEAAAAAAAABAgMEBQYHCAkKC//EALURAAIBAgQEAwQHBQQEAAECdwABAgMRBAUhMQYSQVEHYXETIjKBCBRCkaGxwQkjM1LwFWJy0QoWJDThJfEXGBkaJicoKSo1Njc4OTpDREVGR0hJSlNUVVZXWFlaY2RlZmdoaWpzdHV2d3h5eoKDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uLj5OXm5+jp6vLz9PX29/j5+v/aAAwDAQACEQMRAD8A+uKKKKACipba1lvbiOCCNpZpDtVEGSTXe6X8Hry4iV769jtGIz5caeYR9TkD8s0Aee0V6Hqfwdu4ImexvUumHPlyJ5ZP0OSPzxXA3VpNY3EkFxE0M0ZwyOMEGgCKiiigAooooA9a+Enh+ODTX1aRA087FImP8KA4OPqQfyr0GuW+Glylx4OslQjdEXjcDsdxP8iD+NdTQAVwHxZ8Px3OlLqsaAXFuQsjAfeQnHP0JH5mu/rmfiPcpbeDr/eRmTbGo9SWH9AT+FAHhVFFFABRRVrS9MuNZv4bO1TzJpTgDsPUn2FAHQ+APGD+Gr8wyI81lcEB0QZZW7MB39x3/CvbYpBNGrrkKwBG5Sp/EHkVg+FfBdj4Xt1KIJ7wj57lhz9F9BXQ0ANkkEUbO2dqjJ2gk/kOTXifxA8Yv4kvVt4keGyt2O1HGGZuhYjt7D/Gvbq57xV4LsfFFuxdBBeAfJcqOfo3qKAPBaKtapplxo1/NZ3SeXNEcEdj6EexqrQAV678JvD62elvqki/v7klYyf4Ywf6kfoK8ir6P0ezGn6TZ2yjAhhRPyAoAuUUUUAFFFFAHA/Fnw+t5paapGv7+2IWQj+KMn+hP6mvIq+j9YsxqGk3lswyJoXT8wa+cKAP/9k=)

Bob Smith

__17 days ago

__

Am I right in thinking that msg goes to stderr, but die goes to stdout?  
Seems like the wrong way round to me.

0

Reply

__

[![Maciej
Radzikowski](data:image/jpeg;base64,/9j/4AAQSkZJRgABAQEAYABgAAD//gA7Q1JFQVRPUjogZ2QtanBlZyB2MS4wICh1c2luZyBJSkcgSlBFRyB2NjIpLCBxdWFsaXR5ID0gOTAK/9sAQwADAgIDAgIDAwMDBAMDBAUIBQUEBAUKBwcGCAwKDAwLCgsLDQ4SEA0OEQ4LCxAWEBETFBUVFQwPFxgWFBgSFBUU/9sAQwEDBAQFBAUJBQUJFA0LDRQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQU/8AAEQgAQABAAwEiAAIRAQMRAf/EAB8AAAEFAQEBAQEBAAAAAAAAAAABAgMEBQYHCAkKC//EALUQAAIBAwMCBAMFBQQEAAABfQECAwAEEQUSITFBBhNRYQcicRQygZGhCCNCscEVUtHwJDNicoIJChYXGBkaJSYnKCkqNDU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6g4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2drh4uPk5ebn6Onq8fLz9PX29/j5+v/EAB8BAAMBAQEBAQEBAQEAAAAAAAABAgMEBQYHCAkKC//EALURAAIBAgQEAwQHBQQEAAECdwABAgMRBAUhMQYSQVEHYXETIjKBCBRCkaGxwQkjM1LwFWJy0QoWJDThJfEXGBkaJicoKSo1Njc4OTpDREVGR0hJSlNUVVZXWFlaY2RlZmdoaWpzdHV2d3h5eoKDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uLj5OXm5+jp6vLz9PX29/j5+v/aAAwDAQACEQMRAD8A/SpmqFyPWlZutZ+sXctppd3PBH5s0ULukf8AeYKSB+JqyDC8cfE3wt8OLWO58S63a6SkufLWZvnkx12oMscewrxLVv24/B1tf+XZ6df3doeReSbY1Yeqjkke5xXyd4f8O+NP2kfiLf3l1qss13DITcXVyxMFspOVjReeOvyjAr2+y/Y88L6ZYyzavrdxe3LEnbb/ALtAe/HOc0Ae2fDT9qPwd8TNcTRbeWfTdWkB8mC7ACzkDJCODgnHODgntmvW3fivzr8c/CeL4dNb+JPB11ONR0m4S7ihnbcr7GDAevavtf4PfEeP4rfDjRfEqxC3lvIiJoAciOVWKuv0yDj2IoA7V3zUZpGkA61E1wg70AdCX61DIwIIpGk61DJJgUAfJXhOy0j4IeIviDb6hKbW1XWDPG8aNIfKkQPGuFBP3Wx9RVHxD+0Zov8AZk9xp2m6nfxIRmRrZo4kznG92wFzg8Hn2rs/i54FsfFXjDXgYJdNnfyS00ErL9r/AHSjcRnAIACZGOEGTXkSaL4M+G/gnxBpNxftJ9sKtNEqmTeVPTPPqR160Acbqfxql8aW01nBY2cEsitsh+1+YXyOAdo+XP0PWvff2RvFem6P4IuvDs91HBqY1W4MNnISrsvlxuSAfq35GvEPC8XhaO0aSwtQuDmLzVYb1zwVOePpgV2nwd8K3mufFL+1IeNPsUE7kcbH2soGf9rPT0VqAPqm51dixANVTqDt3xWXM5V+aVZqAPSXuhnrUElzkVRa45qCW72jrQBw/wAZ4lj0VNR+4Yj5Uko7K3TPtn/0Kvj/AMV+G9R8R6Ob53hhtLR3jiESl3Ybjy3IGeT619S/tDePE8EfB7xXqh8l7hLGSK2jnAZXmcbIwVP3huYEj0Br4tX/AISKbwPaS+HL3+07LUbWN5YXkAeKUqN3J6jdn3GKALBWfwnbRzX2oGS2xhInVVC+/FfWf7OJMXw9jvJBtGozNcRg9fLwFU/jtJ+hFfEMWkahrNxbyeIJATaqFNsrbkyPU9+let/ss/Hp7nxv4q8G6zqkK2VtJE+jfaJFQ4IxJCpP3ucEDqPm7dAD7GvoQxLrWeWKnmpY9VQx8nNVZ7lGPFAGh41+IGh/D3RJNX8Q6lDplgrbPMlJJZiCQqqASzYB4AJ4NfHXxe/4KAXUzTWHgPThbRfd/tXUFDSH3SLoPq2f90VyX7fHxEbU/iLZ6BFOxttItV8yLd8onk+cn/vjy6+T/tbzNwMj60Adb4v+JniPx9qUV14j1y91QxklBdTMyRg9dq9F/ACo/hr8eH8HX0tuWk/s5nOIpAT+Ix0rjJ8uhBJwR3rEudORQ3p1xigD6g8VePbKbw4NUt51SG55DY5OewHc183XOuJd6ncMu7znfeSOQPbPrWNPHc3EMcEk8rW8efLhLnauTk4H1pbKx8lwQMc0AfRHwt/ar8beAI4rZr/+2tLjAH2TUGL7V9Ef7y+wyQPSvsz4N/tD6D8XbdorYtYaxEm+XT52BbHdkb+Nffg+oFfmMJBFCx6Edvxr0/8AZ38WtoPxh8KTxybY5roWr88ES/u+f++s/hQB/9k=)](https://betterdev.blog/author/maciej-
radzikowski/)

Author

[Maciej Radzikowski](https://betterdev.blog/author/maciej-radzikowski/)

__16 days ago

__

__Reply to   Bob Smith

No, why? die is using msg to print text, so it will go to stderr.

0

Reply

![Adrian](data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD//gA7Q1JFQVRPUjogZ2QtanBlZyB2MS4wICh1c2luZyBJSkcgSlBFRyB2NjIpLCBxdWFsaXR5ID0gOTAK/9sAQwADAgIDAgIDAwMDBAMDBAUIBQUEBAUKBwcGCAwKDAwLCgsLDQ4SEA0OEQ4LCxAWEBETFBUVFQwPFxgWFBgSFBUU/9sAQwEDBAQFBAUJBQUJFA0LDRQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQU/8AAEQgAQABAAwEiAAIRAQMRAf/EAB8AAAEFAQEBAQEBAAAAAAAAAAABAgMEBQYHCAkKC//EALUQAAIBAwMCBAMFBQQEAAABfQECAwAEEQUSITFBBhNRYQcicRQygZGhCCNCscEVUtHwJDNicoIJChYXGBkaJSYnKCkqNDU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6g4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2drh4uPk5ebn6Onq8fLz9PX29/j5+v/EAB8BAAMBAQEBAQEBAQEAAAAAAAABAgMEBQYHCAkKC//EALURAAIBAgQEAwQHBQQEAAECdwABAgMRBAUhMQYSQVEHYXETIjKBCBRCkaGxwQkjM1LwFWJy0QoWJDThJfEXGBkaJicoKSo1Njc4OTpDREVGR0hJSlNUVVZXWFlaY2RlZmdoaWpzdHV2d3h5eoKDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uLj5OXm5+jp6vLz9PX29/j5+v/aAAwDAQACEQMRAD8A+uKKKKACipba1lvbiOCCNpZpDtVEGSTXe6X8Hry4iV769jtGIz5caeYR9TkD8s0Aee0V6Hqfwdu4ImexvUumHPlyJ5ZP0OSPzxXA3VpNY3EkFxE0M0ZwyOMEGgCKiiigAooooA9a+Enh+ODTX1aRA087FImP8KA4OPqQfyr0GuW+Glylx4OslQjdEXjcDsdxP8iD+NdTQAVwHxZ8Px3OlLqsaAXFuQsjAfeQnHP0JH5mu/rmfiPcpbeDr/eRmTbGo9SWH9AT+FAHhVFFFABRRVrS9MuNZv4bO1TzJpTgDsPUn2FAHQ+APGD+Gr8wyI81lcEB0QZZW7MB39x3/CvbYpBNGrrkKwBG5Sp/EHkVg+FfBdj4Xt1KIJ7wj57lhz9F9BXQ0ANkkEUbO2dqjJ2gk/kOTXifxA8Yv4kvVt4keGyt2O1HGGZuhYjt7D/Gvbq57xV4LsfFFuxdBBeAfJcqOfo3qKAPBaKtapplxo1/NZ3SeXNEcEdj6EexqrQAV678JvD62elvqki/v7klYyf4Ywf6kfoK8ir6P0ezGn6TZ2yjAhhRPyAoAuUUUUAFFFFAHA/Fnw+t5paapGv7+2IWQj+KMn+hP6mvIq+j9YsxqGk3lswyJoXT8wa+cKAP/9k=)

Adrian

__17 days ago

__

Hey, nice article, i really like it.  
Only thing i don’t agree with is the change directory part.  
I would much rather instead of that have the script determine its parent
directory, if at all needed.  
This article comes to mind which solved this problem for me:
<https://stackoverflow.com/questions/59895/how-to-get-the-source-directory-of-
a-bash-script-from-within-the-script-itself>

0

Reply

__

[![Maciej
Radzikowski](data:image/jpeg;base64,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)](https://betterdev.blog/author/maciej-
radzikowski/)

Author

[Maciej Radzikowski](https://betterdev.blog/author/maciej-radzikowski/)

__16 days ago

__

__Reply to   Adrian

Yeah, it was the most frequently pointed out thing in the template, and I have
to agree. Now the template is updated to not change the dir.

0

Reply

![jvh](data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD//gA7Q1JFQVRPUjogZ2QtanBlZyB2MS4wICh1c2luZyBJSkcgSlBFRyB2NjIpLCBxdWFsaXR5ID0gOTAK/9sAQwADAgIDAgIDAwMDBAMDBAUIBQUEBAUKBwcGCAwKDAwLCgsLDQ4SEA0OEQ4LCxAWEBETFBUVFQwPFxgWFBgSFBUU/9sAQwEDBAQFBAUJBQUJFA0LDRQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQU/8AAEQgAQABAAwEiAAIRAQMRAf/EAB8AAAEFAQEBAQEBAAAAAAAAAAABAgMEBQYHCAkKC//EALUQAAIBAwMCBAMFBQQEAAABfQECAwAEEQUSITFBBhNRYQcicRQygZGhCCNCscEVUtHwJDNicoIJChYXGBkaJSYnKCkqNDU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6g4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2drh4uPk5ebn6Onq8fLz9PX29/j5+v/EAB8BAAMBAQEBAQEBAQEAAAAAAAABAgMEBQYHCAkKC//EALURAAIBAgQEAwQHBQQEAAECdwABAgMRBAUhMQYSQVEHYXETIjKBCBRCkaGxwQkjM1LwFWJy0QoWJDThJfEXGBkaJicoKSo1Njc4OTpDREVGR0hJSlNUVVZXWFlaY2RlZmdoaWpzdHV2d3h5eoKDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uLj5OXm5+jp6vLz9PX29/j5+v/aAAwDAQACEQMRAD8A+uKKKKACipba1lvbiOCCNpZpDtVEGSTXe6X8Hry4iV769jtGIz5caeYR9TkD8s0Aee0V6Hqfwdu4ImexvUumHPlyJ5ZP0OSPzxXA3VpNY3EkFxE0M0ZwyOMEGgCKiiigAooooA9a+Enh+ODTX1aRA087FImP8KA4OPqQfyr0GuW+Glylx4OslQjdEXjcDsdxP8iD+NdTQAVwHxZ8Px3OlLqsaAXFuQsjAfeQnHP0JH5mu/rmfiPcpbeDr/eRmTbGo9SWH9AT+FAHhVFFFABRRVrS9MuNZv4bO1TzJpTgDsPUn2FAHQ+APGD+Gr8wyI81lcEB0QZZW7MB39x3/CvbYpBNGrrkKwBG5Sp/EHkVg+FfBdj4Xt1KIJ7wj57lhz9F9BXQ0ANkkEUbO2dqjJ2gk/kOTXifxA8Yv4kvVt4keGyt2O1HGGZuhYjt7D/Gvbq57xV4LsfFFuxdBBeAfJcqOfo3qKAPBaKtapplxo1/NZ3SeXNEcEdj6EexqrQAV678JvD62elvqki/v7klYyf4Ywf6kfoK8ir6P0ezGn6TZ2yjAhhRPyAoAuUUUUAFFFFAHA/Fnw+t5paapGv7+2IWQj+KMn+hP6mvIq+j9YsxqGk3lswyJoXT8wa+cKAP/9k=)

jvh

__17 days ago

__

The failure mode of `script_dir=...` deserves a little more explanation. My
first reaction is always to add `|| exit` on anything that does a `cd` but
that isn’t needed here because you have `&& pwd -P`. Except that bash disables
`-e` when evaluating a substitution inside a subshell (I have no idea why that
seems like a good idea). So if the `cd` fails, it doesn’t terminate the
subshell but because you have `&& pwd -P` the exit status of the failing `cd`
is the exit status of the subshell setting `script_dir` and so the entire
assignment fails and the shell exits.  
Unfortunately it exits silently because you’re discarding stderr so when
you’re falling foul of the inevitable 🙂 symlink race condition, the script
just silently and mysteriously does nothing.  
You’re also in danger, I think, of Mysterious Bad Behaviour because you’re
trusting whatever PATH is set to. You’re also trusting that any functions in
the environment `export -f` don’t do unexpected things. (That last one is
quite difficult, if not impossible, to guard against.)

0

Reply

__

[![Maciej
Radzikowski](data:image/jpeg;base64,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)](https://betterdev.blog/author/maciej-
radzikowski/)

Author

[Maciej Radzikowski](https://betterdev.blog/author/maciej-radzikowski/)

__15 days ago

__

__Reply to   jvh

Wow, that’s a very in-deep analysis of that part. Thank you. You are right,
having a script mysteriously exiting on one of the first lines like that would
be amusing to debug.

0

Reply

![William
Pursell](data:image/jpeg;base64,/9j/4AAQSkZJRgABAQEAYABgAAD//gA7Q1JFQVRPUjogZ2QtanBlZyB2MS4wICh1c2luZyBJSkcgSlBFRyB2NjIpLCBxdWFsaXR5ID0gOTAK/9sAQwADAgIDAgIDAwMDBAMDBAUIBQUEBAUKBwcGCAwKDAwLCgsLDQ4SEA0OEQ4LCxAWEBETFBUVFQwPFxgWFBgSFBUU/9sAQwEDBAQFBAUJBQUJFA0LDRQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQU/8AAEQgAQABAAwEiAAIRAQMRAf/EAB8AAAEFAQEBAQEBAAAAAAAAAAABAgMEBQYHCAkKC//EALUQAAIBAwMCBAMFBQQEAAABfQECAwAEEQUSITFBBhNRYQcicRQygZGhCCNCscEVUtHwJDNicoIJChYXGBkaJSYnKCkqNDU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6g4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2drh4uPk5ebn6Onq8fLz9PX29/j5+v/EAB8BAAMBAQEBAQEBAQEAAAAAAAABAgMEBQYHCAkKC//EALURAAIBAgQEAwQHBQQEAAECdwABAgMRBAUhMQYSQVEHYXETIjKBCBRCkaGxwQkjM1LwFWJy0QoWJDThJfEXGBkaJicoKSo1Njc4OTpDREVGR0hJSlNUVVZXWFlaY2RlZmdoaWpzdHV2d3h5eoKDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uLj5OXm5+jp6vLz9PX29/j5+v/aAAwDAQACEQMRAD8A+uKKKKACipba1lvbiOCCNpZpDtVEGSTXe6X8Hry4iV769jtGIz5caeYR9TkD8s0Aee0V6Hqfwdu4ImexvUumHPlyJ5ZP0OSPzxXA3VpNY3EkFxE0M0ZwyOMEGgCKiiigAooooA9a+Enh+ODTX1aRA087FImP8KA4OPqQfyr0GuW+Glylx4OslQjdEXjcDsdxP8iD+NdTQAVwHxZ8Px3OlLqsaAXFuQsjAfeQnHP0JH5mu/rmfiPcpbeDr/eRmTbGo9SWH9AT+FAHhVFFFABRRVrS9MuNZv4bO1TzJpTgDsPUn2FAHQ+APGD+Gr8wyI81lcEB0QZZW7MB39x3/CvbYpBNGrrkKwBG5Sp/EHkVg+FfBdj4Xt1KIJ7wj57lhz9F9BXQ0ANkkEUbO2dqjJ2gk/kOTXifxA8Yv4kvVt4keGyt2O1HGGZuhYjt7D/Gvbq57xV4LsfFFuxdBBeAfJcqOfo3qKAPBaKtapplxo1/NZ3SeXNEcEdj6EexqrQAV678JvD62elvqki/v7klYyf4Ywf6kfoK8ir6P0ezGn6TZ2yjAhhRPyAoAuUUUUAFFFFAHA/Fnw+t5paapGv7+2IWQj+KMn+hP6mvIq+j9YsxqGk3lswyJoXT8wa+cKAP/9k=)

William Pursell

__14 days ago

__

Providing a link to some of the arguments against errexit is useful, but I
think you are overlooking those arguments too glibly. In particular, I’ll
quote from the article you link help ensure people don’t miss it. You should
never use `set -e`:  
set -e has changed behavior between bash versions, triggering fatal errors in
one version, ignoring the same non-zero return value in another. In addition,
whether a command returning non-zero causes a fatal error or not depends on
the context it is run in. So in practice, you have to go over every command
and decide how to handle their return value anyway. It’s the only way to get
reliable error handling. set -e adds nothing useful to the table.  
See  <http://mywiki.wooledge.org/BashFAQ/105>  for some examples of the weird
cases you have to deal with.

__Last edited 14 days ago by William Pursell

0

Reply

__

[![Maciej
Radzikowski](data:image/jpeg;base64,/9j/4AAQSkZJRgABAQEAYABgAAD//gA7Q1JFQVRPUjogZ2QtanBlZyB2MS4wICh1c2luZyBJSkcgSlBFRyB2NjIpLCBxdWFsaXR5ID0gOTAK/9sAQwADAgIDAgIDAwMDBAMDBAUIBQUEBAUKBwcGCAwKDAwLCgsLDQ4SEA0OEQ4LCxAWEBETFBUVFQwPFxgWFBgSFBUU/9sAQwEDBAQFBAUJBQUJFA0LDRQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQU/8AAEQgAQABAAwEiAAIRAQMRAf/EAB8AAAEFAQEBAQEBAAAAAAAAAAABAgMEBQYHCAkKC//EALUQAAIBAwMCBAMFBQQEAAABfQECAwAEEQUSITFBBhNRYQcicRQygZGhCCNCscEVUtHwJDNicoIJChYXGBkaJSYnKCkqNDU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6g4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2drh4uPk5ebn6Onq8fLz9PX29/j5+v/EAB8BAAMBAQEBAQEBAQEAAAAAAAABAgMEBQYHCAkKC//EALURAAIBAgQEAwQHBQQEAAECdwABAgMRBAUhMQYSQVEHYXETIjKBCBRCkaGxwQkjM1LwFWJy0QoWJDThJfEXGBkaJicoKSo1Njc4OTpDREVGR0hJSlNUVVZXWFlaY2RlZmdoaWpzdHV2d3h5eoKDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uLj5OXm5+jp6vLz9PX29/j5+v/aAAwDAQACEQMRAD8A/SpmqFyPWlZutZ+sXctppd3PBH5s0ULukf8AeYKSB+JqyDC8cfE3wt8OLWO58S63a6SkufLWZvnkx12oMscewrxLVv24/B1tf+XZ6df3doeReSbY1Yeqjkke5xXyd4f8O+NP2kfiLf3l1qss13DITcXVyxMFspOVjReeOvyjAr2+y/Y88L6ZYyzavrdxe3LEnbb/ALtAe/HOc0Ae2fDT9qPwd8TNcTRbeWfTdWkB8mC7ACzkDJCODgnHODgntmvW3fivzr8c/CeL4dNb+JPB11ONR0m4S7ihnbcr7GDAevavtf4PfEeP4rfDjRfEqxC3lvIiJoAciOVWKuv0yDj2IoA7V3zUZpGkA61E1wg70AdCX61DIwIIpGk61DJJgUAfJXhOy0j4IeIviDb6hKbW1XWDPG8aNIfKkQPGuFBP3Wx9RVHxD+0Zov8AZk9xp2m6nfxIRmRrZo4kznG92wFzg8Hn2rs/i54FsfFXjDXgYJdNnfyS00ErL9r/AHSjcRnAIACZGOEGTXkSaL4M+G/gnxBpNxftJ9sKtNEqmTeVPTPPqR160Acbqfxql8aW01nBY2cEsitsh+1+YXyOAdo+XP0PWvff2RvFem6P4IuvDs91HBqY1W4MNnISrsvlxuSAfq35GvEPC8XhaO0aSwtQuDmLzVYb1zwVOePpgV2nwd8K3mufFL+1IeNPsUE7kcbH2soGf9rPT0VqAPqm51dixANVTqDt3xWXM5V+aVZqAPSXuhnrUElzkVRa45qCW72jrQBw/wAZ4lj0VNR+4Yj5Uko7K3TPtn/0Kvj/AMV+G9R8R6Ob53hhtLR3jiESl3Ybjy3IGeT619S/tDePE8EfB7xXqh8l7hLGSK2jnAZXmcbIwVP3huYEj0Br4tX/AISKbwPaS+HL3+07LUbWN5YXkAeKUqN3J6jdn3GKALBWfwnbRzX2oGS2xhInVVC+/FfWf7OJMXw9jvJBtGozNcRg9fLwFU/jtJ+hFfEMWkahrNxbyeIJATaqFNsrbkyPU9+let/ss/Hp7nxv4q8G6zqkK2VtJE+jfaJFQ4IxJCpP3ucEDqPm7dAD7GvoQxLrWeWKnmpY9VQx8nNVZ7lGPFAGh41+IGh/D3RJNX8Q6lDplgrbPMlJJZiCQqqASzYB4AJ4NfHXxe/4KAXUzTWHgPThbRfd/tXUFDSH3SLoPq2f90VyX7fHxEbU/iLZ6BFOxttItV8yLd8onk+cn/vjy6+T/tbzNwMj60Adb4v+JniPx9qUV14j1y91QxklBdTMyRg9dq9F/ACo/hr8eH8HX0tuWk/s5nOIpAT+Ix0rjJ8uhBJwR3rEudORQ3p1xigD6g8VePbKbw4NUt51SG55DY5OewHc183XOuJd6ncMu7znfeSOQPbPrWNPHc3EMcEk8rW8efLhLnauTk4H1pbKx8lwQMc0AfRHwt/ar8beAI4rZr/+2tLjAH2TUGL7V9Ef7y+wyQPSvsz4N/tD6D8XbdorYtYaxEm+XT52BbHdkb+Nffg+oFfmMJBFCx6Edvxr0/8AZ38WtoPxh8KTxybY5roWr88ES/u+f++s/hQB/9k=)](https://betterdev.blog/author/maciej-
radzikowski/)

Author

[Maciej Radzikowski](https://betterdev.blog/author/maciej-radzikowski/)

__14 days ago

__

__Reply to   William Pursell

I start to have a feeling that posting

> use “set -e” in your scripts!

on unix forum is like posting “tabs vs spaces” on any programming channel 😉

__Last edited 14 days ago by Maciej Radzikowski

0

Reply

![Eric
Nemchik](data:image/jpeg;base64,/9j/4AAQSkZJRgABAQEAYABgAAD//gA7Q1JFQVRPUjogZ2QtanBlZyB2MS4wICh1c2luZyBJSkcgSlBFRyB2NjIpLCBxdWFsaXR5ID0gOTAK/9sAQwADAgIDAgIDAwMDBAMDBAUIBQUEBAUKBwcGCAwKDAwLCgsLDQ4SEA0OEQ4LCxAWEBETFBUVFQwPFxgWFBgSFBUU/9sAQwEDBAQFBAUJBQUJFA0LDRQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQU/8AAEQgAQABAAwEiAAIRAQMRAf/EAB8AAAEFAQEBAQEBAAAAAAAAAAABAgMEBQYHCAkKC//EALUQAAIBAwMCBAMFBQQEAAABfQECAwAEEQUSITFBBhNRYQcicRQygZGhCCNCscEVUtHwJDNicoIJChYXGBkaJSYnKCkqNDU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6g4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2drh4uPk5ebn6Onq8fLz9PX29/j5+v/EAB8BAAMBAQEBAQEBAQEAAAAAAAABAgMEBQYHCAkKC//EALURAAIBAgQEAwQHBQQEAAECdwABAgMRBAUhMQYSQVEHYXETIjKBCBRCkaGxwQkjM1LwFWJy0QoWJDThJfEXGBkaJicoKSo1Njc4OTpDREVGR0hJSlNUVVZXWFlaY2RlZmdoaWpzdHV2d3h5eoKDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uLj5OXm5+jp6vLz9PX29/j5+v/aAAwDAQACEQMRAD8A9WvPEEGpWYht/nVsIscXU9gFrrk8L+J9A1Ipc6RfWmj7nWK6aBpiFViNz7BxkYIzjjJ4rjfhD4b0PwOul+KvGXiKLSdMtrxTBPcSLHDPInzFVLctjB4HPBx3x137R/7efgTwz4JB8Kapb+Kb28zAqWpO1BjlmbjjGfzrgpyjXkqqnZLp3/zN5KdGEqbp3b6vp/l8zspFvLK0vYLe/iNxCqt9pmixFFn+98wyTzgZHSrHjD4b6T490creXdxZ2FwYYbh41RpVO5DkEg7TnHbBH1zX5yXfx91X4zeJPN8Ray2j6DYr532Sy446BIk6b2zjc2cDJOcYPsfgr9qjxNrOi+H/AA/ZaWv/AAjNneJDHcvIxmaOL5yu/cN7Zxkhe+MdMa82tnsUo2ScXqfV2m/A3wzBYTaRDcSX2kwOITNLDGk7u6jnzQAcgsuB6jkHOK42X4PJ4I0+zntdQuLmxEjF4pBukiUHLbWQZ3DBIGOSCR6VyPw6/ajuJPG3iazhhhl0vyILhI3ZmbcybWHJwVwoOPc/SvQx8cdL8S314iv9imuRC6O4ZTvRiGG046q3H0J7VtZyWgva66kd747TTrNGuZw8bMwgnB3CeMYKvkeoIrmdR+IFtf28qq+9SMYI4Ncbo+r+HofF39lz6qkmm3kkt3/ZEw+S3Y4ZiGyNqZJwAeCa+hNN/ZZ8K6xaQXcV1eWIYCSSCGUspBGQFLcj65P4Vz0qeKjStO0pLR9L9vvVvmZ1alB1bRuov8uv3ann/wAfF8PfFD9liaSzsks7fR7a9tzDyiROtrJgrjIJyIyM+pPFflJ45nt/DmmaZp9qzTwyxFy/RUl43DIzvwGHIOMkjsK/Sv8AaH+I+hfC/wCF8fw80S1OqaN4wjXVNJ1xZ45EaLcjHcB8xPyAD5cMCACeQPzb+MfifS9UsofD+mWxuLm0l82S8Uj5GAI2rjOc559MDuOM6aldXeiOl7Pz6nC2WvBLmGOWV0hMg8zy+SBnk49cV9A/Cn4n+HtZ+JVlbawur2fhGCE2kcGhqHulVgVGxT95mJ578k9hXzFp8sFpMHuIjI0ZBMTHG7nkZxxXW+E/Eup+C9ZtNatbvydc3NJaJE37yAgYEhA6EAnb3GM+meuKUnaWxyVE6acovXofd/x68C+EP2UvjFFZQ63dwaNqvh+K5V7yPfIH85k2gInooPI9ea82Hx907xDFc6Xplv5kiIrpqFyRGS4IGVi57Fzyfyxmvnb4kePfE/xO1Z9T8S6zd6lqqlLdTeSO7ogz3boMt0Hoa9o8d/s5eI/gN8MfDnibxDe6RZNqCkjSIZg+o/MpIldccdQMA4GVBGTXdSTUNjiqThzr3tWdD4O1q81Kzvde8N6it1qugo8d1oswCm4t5FA3B8n+6V6ZGR3Oa94+DH/BRWXwZpn2Dxr4d1aS3UrHFdwsk2xc4+bCjpkc8n2r4y/Z68ZNonxD1E3TQLZvbPG/mr87bmBA68EZI/AjvX0F8IvC+heOfi7oWhIkdzbJcrqFysmNqwxuuNwPVC5jDD+6W9K82dWSk+V2uejGlHRzV7HzF8XfF+p2t3FoJuLiYiBVgu5NybIjyFhQsSi5z19TxzXnNzYT+FXtp9UhKNKA0VvghnTpkZ6D39fxrCg1ybxJqqvqNw093OyoZZmOD0AyRzj6Vra/c2Oga3teObUpY412C5n3LF6D1I9Bx2rdQSVjklKV7XPQtRuNH+JF1aDQPD0kGr2VlmK0EY33UgOWeQrn92iKcHrk84UZHu37P3hbwD4r1GLUPE2j2Ov6nKGhuNDvLlrC6R+AphnDBWxtAClsnsvevi/QPE994c1mz1XTL24sr+CUSLNA5jZCDkFWByDX2L8QLr4d/Hi+8Kah8Odbl07x/e2ka6vpt9GtvFLdqiqzRyDADOwJOeOSSVr1sDGDd3G77dz5/NHVpwVNT5Y/zb29d9Pl+B6d8YPBvwx8H6RLd2XhCx8Ka1BHzpcl42o6i8o5UOxby4TwPvbWI+7u6V81/FO/8S+ILC31LxRZy2FteKTp0EzkyyhQCDjPK7hk478HnFe4fDTwx4C+AOuPf/HnXzeeILCDzNO8M2p+1sZOo80rlVyf4cjrya+P/iP8XNY8feItU1K/v7i/aWTakt1IXYqCcD0VQOAijao4HUk64u0I2tZvp/V7meVOc53vzRT3a19FtZfLX8Xzmia8dK1Bbhg7YbJZTgnmvof4XfEybQdG8Sa3poH9o6haGxtJJHwVxgMRg5DfvWC5GDk8/KSPlk3ODXZ+FfF2NOh0yYQQQxzrIJEhw/GcsxAyeCf0r56pBtaH16qO+uxpfB/4DeJPi8l1HoOkzanJA8Ku0ciRxweYzKrSFudvyk/LkgDpWb8V/A978PvHGp+HNWs4LW70+UwTTWhZkkPUOucZUgg9B16Cv0p/ZG8S+A/CPhCbQbWGTTtYKSX148oULcsq9IyMcBVAC+g7nJP5w/EL4gzfFLx34o8RTWZtrbVry4u4bd2EjW+9y6oHIHA6ZAH9KuEnOTXRHEm0ry0ODNoYijBlkQ/xL/UVc0u6kttQWWCR0kHKNGcEH+ldr4a+D2s+JtIudV06BpoIk/hGTnpiuaHgXxBp1wzPpF+PK5bbauRgdzgdK7I3i0zndWFRSjcbrV5eTXk8t3O81wOGlmcsx/E1hsNyArkA+ta76Xfa7fbYbeRp3JbythGfoKl1Dw/feH7oQ3NltmCDiRTwTzRUbm7jhONOKiYT2csce9xtB6Z6t9KtaIPJ1FJX2xooILS5wOMDp35pJTtfNwzF/UtmrNs8SrlfmB6nv/8AWrBqx1xd1c//2Q==)

Eric Nemchik

__14 days ago

__

Very good stuff here. Some things I’ll apply to my various projects. Much of
what you’re doing is similar to (albeit smaller than) a project I consider to
be my greatest bash project
<https://github.com/GhostWriters/DockSTARTer/blob/master/main.sh> which I made
with very similar principals in mind mostly derived from resources I
documented here
<https://github.com/GhostWriters/DockSTARTer/blob/master/.github/CONTRIBUTING.md#shell-
scripts>

I will very likely take a shot at getting somewhere down the middle between
what you have and what I have, and I’ll reach out if I come up with anything
worth discussing.

Very happy to see you’ve written this!

0

Reply

![digi](data:image/jpeg;base64,/9j/4AAQSkZJRgABAQEAYABgAAD//gA7Q1JFQVRPUjogZ2QtanBlZyB2MS4wICh1c2luZyBJSkcgSlBFRyB2NjIpLCBxdWFsaXR5ID0gOTAK/9sAQwADAgIDAgIDAwMDBAMDBAUIBQUEBAUKBwcGCAwKDAwLCgsLDQ4SEA0OEQ4LCxAWEBETFBUVFQwPFxgWFBgSFBUU/9sAQwEDBAQFBAUJBQUJFA0LDRQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQUFBQU/8AAEQgAQABAAwEiAAIRAQMRAf/EAB8AAAEFAQEBAQEBAAAAAAAAAAABAgMEBQYHCAkKC//EALUQAAIBAwMCBAMFBQQEAAABfQECAwAEEQUSITFBBhNRYQcicRQygZGhCCNCscEVUtHwJDNicoIJChYXGBkaJSYnKCkqNDU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6g4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2drh4uPk5ebn6Onq8fLz9PX29/j5+v/EAB8BAAMBAQEBAQEBAQEAAAAAAAABAgMEBQYHCAkKC//EALURAAIBAgQEAwQHBQQEAAECdwABAgMRBAUhMQYSQVEHYXETIjKBCBRCkaGxwQkjM1LwFWJy0QoWJDThJfEXGBkaJicoKSo1Njc4OTpDREVGR0hJSlNUVVZXWFlaY2RlZmdoaWpzdHV2d3h5eoKDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uLj5OXm5+jp6vLz9PX29/j5+v/aAAwDAQACEQMRAD8A+uKKKKACipba1lvbiOCCNpZpDtVEGSTXe6X8Hry4iV769jtGIz5caeYR9TkD8s0Aee0V6Hqfwdu4ImexvUumHPlyJ5ZP0OSPzxXA3VpNY3EkFxE0M0ZwyOMEGgCKiiigAooooA9a+Enh+ODTX1aRA087FImP8KA4OPqQfyr0GuW+Glylx4OslQjdEXjcDsdxP8iD+NdTQAVwHxZ8Px3OlLqsaAXFuQsjAfeQnHP0JH5mu/rmfiPcpbeDr/eRmTbGo9SWH9AT+FAHhVFFFABRRVrS9MuNZv4bO1TzJpTgDsPUn2FAHQ+APGD+Gr8wyI81lcEB0QZZW7MB39x3/CvbYpBNGrrkKwBG5Sp/EHkVg+FfBdj4Xt1KIJ7wj57lhz9F9BXQ0ANkkEUbO2dqjJ2gk/kOTXifxA8Yv4kvVt4keGyt2O1HGGZuhYjt7D/Gvbq57xV4LsfFFuxdBBeAfJcqOfo3qKAPBaKtapplxo1/NZ3SeXNEcEdj6EexqrQAV678JvD62elvqki/v7klYyf4Ywf6kfoK8ir6P0ezGn6TZ2yjAhhRPyAoAuUUUUAFFFFAHA/Fnw+t5paapGv7+2IWQj+KMn+hP6mvIq+j9YsxqGk3lswyJoXT8wa+cKAP/9k=)

digi

__13 days ago

__

Good stuff!  
I write a lot of Bash, I tend to do similar things. I’ve tried to modular
approach and that did not work so well, now I tend to use a standard header
for any script that I write. I usually always include printf wrapper functions
and some basic logging:

    
    
    function do_pf() {
    
        MSG="$1"
    
        printf '%s\n' "$MSG"
    
    }
    
    function do_npf() {
    
        MSG="$1"
    
        printf '%s' "$MSG"
    
    }
    
    

and if you want something like printed borders:

    
    
    BLCHAR='-'
    
    BORDER='80'
    
    
    
    
    function do_bl() {
    
        BCHAR="$1"
    
    
    
    
        if [[ "$BCHAR" == '' ]];
    
        then
    
            BCHAR="$BLCHAR"
    
        fi
    
    
    
    
        printf -v borderline '%*s' "$BORDER"
    
        echo ${borderline// /$BCHAR}
    
    }
    
    
    
    

And for logging:

    
    
    function do_log() {
    
           LOGMSG="$1"
    
           RUNLOGFILE="$RUNLOG"
    
           LOGDATE=date "+%m-%d-%Y.%H%M.%N"
    
           printf '%s\n' "$LOGDATE|$LOGMSG" >> "$RUNLOGFILE"
    
    }
    

A typical function would utilize the logging like this:

    
    
    function hello_any_function() {
          do_log "${FUNCNAME[0]}"
          
           do_pf "hello"
          
          }
    

__Last edited 13 days ago by digi

0

Reply

![Jie
Zheng](data:image/jpeg;base64,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)

[Jie Zheng](http://www.jiezheng.org)

__4 days ago

__

What a nice template here. It’s really a style guide for bash.  
May i recommend another functionality to be include in the template, that is
daemon.  
A daemon functionality is also minimal. Start a process in background and get
the pid, shutdown a process using a pid file. This feature is needed for daily
usage.

0

Reply

Search for:

##### Hi, I’m Maciej

![Maciej
Radzikowski](data:image/jpeg;base64,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)

I'm a Software Developer and Architect. I do backend, serverless AWS, a bit of
frontend, and really - whatever needs to be done.

Here I share tips, recipes, hacks, solutions. And how to be a better
developer.

Find me on:   [__](https://github.com/m-radzikowski)
[__](https://twitter.com/radzikowski_m)
[__](https://www.linkedin.com/in/mradzikowski/)

[Learn a little bit more...](https://betterdev.blog/about/)

##### Newsletter

Notice: JavaScript is required for this content.

##### Recent Posts

  * [Minimal safe Bash script template](https://betterdev.blog/minimal-safe-bash-script-template/)
  * [Auto-generated website environment parameters](https://betterdev.blog/auto-generated-website-environment-parameters/)
  * [My AWS toolbox – tools, plugins and applications](https://betterdev.blog/my-aws-toolbox/)
  * [Serverless Swagger UI for API Gateway](https://betterdev.blog/serverless-swagger-ui-for-api-gateway/)
  * [Command line arguments anatomy explained with examples](https://betterdev.blog/command-line-arguments-anatomy-explained/)

##### Latest Series

    * [Basic Git configuration for better and faster work](https://betterdev.blog/series/basic-git-configuration/ "Basic Git configuration for better and faster work")

##### Categories

  * [AWS](https://betterdev.blog/category/aws/)
  * [Programming](https://betterdev.blog/category/programming/)
  * [Tools](https://betterdev.blog/category/tools/)

##### Tags

[api](https://betterdev.blog/tag/api/)
[architecture](https://betterdev.blog/tag/architecture/)
[aws](https://betterdev.blog/tag/aws/)
[bash](https://betterdev.blog/tag/bash/)
[cli](https://betterdev.blog/tag/cli/)
[cloud](https://betterdev.blog/tag/cloud/)
[documentation](https://betterdev.blog/tag/documentation/)
[frontend](https://betterdev.blog/tag/frontend/)
[git](https://betterdev.blog/tag/git/)
[level:beginner](https://betterdev.blog/tag/beginner/)
[level:intermediate](https://betterdev.blog/tag/intermediate/)
[plugins](https://betterdev.blog/tag/plugins/)
[serverless](https://betterdev.blog/tag/serverless/)
[serverless_framework](https://betterdev.blog/tag/serverless_framework/)
[shell](https://betterdev.blog/tag/shell/)
[swagger](https://betterdev.blog/tag/swagger/)

  * [Series](https://betterdev.blog/series/)
  * [About](https://betterdev.blog/about/)
  * [Contact](https://betterdev.blog/contact/)
  * [Privacy Policy](https://betterdev.blog/privacy-policy/)

Hestia | Developed by [ThemeIsle](https://themeisle.com)

41

0

Comment and share your thoughts!x

()

x

| Reply

Insert

We use cookies to ensure that we give you the best experience on our website.
If you continue to use this site we will assume that you are happy with
it.OK[](javascript:;)

