![[Pasted image 20230726110859.png]]
I managed to build a bridge between [Termux](https://termux.com/) and [Minimalistic Text](https://play.google.com/store/apps/details?id=de.devmil.minimaltext) using [Tasker](https://tasker.joaoapps.com/). I use it to display the last 20 lines of the [#termux irc channel](https://gitter.im/termux/termux) as you can see in the picture. I've done it without having Tasker check a file every two minutes. The Task is directly called from the script.

_This tutorial is not Termux specific and should work with any terminal emulator_

#### Step 1: Creating the script

All you have to do is write your output to a file in `/sdcard/`. In this example I am grabbing the last 20 lines of log of the [#termux irc channel](https://gitter.im/termux/termux) from my server.

```
while true; do
  # You can basically add your own commands here. They just have to write
  # their output to `/sdcard/widget`

  # For maximum battery and bandwidth efficiency tail and cut are
  # executed on the server
  # the cut command removes the timestamps
  #
  # for this to work you need to have placed your public key on the server.
  # Otherwise you will need to enter your password every two minutes
  ssh user@example.com "cat ~/.weechat/logs/irc.freenode.#termux.weechatlog |tail -n 20 | cut -c 21-">/sdcard/widget

  # This sends an Intent. This is how we'll call the Tasker task which
  # updates the widget. "net.dinglish.tasker" has to be there every
  # time for tasker to receive the intent. The last part is the name
  # of the intent which you can change if you want more than one.
  # This normally produces a bit of useless output. I am removing #
  #that with `>/dev/null`
  am broadcast -a net.dinglish.tasker.updatewidget --user 0 >/dev/null

  # sleep for 120 seconds. How often it should update the widget.
  sleep 120
done
```

If you run this it will download the last 20 lines of the log from a server, paste it into `/sdcard/widget` and call Tasker with an Intent.

You should also create the file `/sdcard/widget` now. Simply do `touch /sdcard/widget`.
![[Pasted image 20230726110932.png]]
{ .right}

#### Step 2: Create a Tasker profile

1. Create a new profile
2. Choose "Event"
3. In the "Select Event Category" dialog choose "System"->"Intent Received"
4. As Action define `net.dinglish.tasker.updatewidget`

This profile will now be called whenever it recieves the "updatewidget" intent. This is a usefull way to extend the functionality of Termux. I also use it to kick of some [Foldersync](https://play.google.com/store/apps/details?id=dk.tacit.android.foldersync.lite) jobs from the terminal.

#### Step 3: Create the Task

![[Pasted image 20230726111009.png]]

1. Tap "New Task" and give it a name
2. Tap + to add a new Action
3. Choose "File"->"Read File"
4. Tap 🔍 and choose `/sdcard/widget`.
5. Under "To Var" enter `%Widget`
6. Tap + again to add another new Action
7. Choose "Plugin"->"Minimalistic Text"->"Minimalistic Text"
8. Click the pen to edit the configuration
9. Enter `%Widget` for both variable name and variable content

#### Step 4: Configure Minimalistic Text

1. Add a Minimalistic Text widget to your homescreen
2. Choose any preset
3. In the "layout" tab remove remove all rows. Now you have a blank widget
4. Add a new element with +
5. Switch "Misc" Tab and tick "Locale variable"
6. Tap "OK"
7. Click on the new "Locale variable" element
8. In the popup enter `%Widget` as a the "Variable name"
9. "OK" and Save

![[Pasted image 20230726111030.png]] ![[Pasted image 20230726111034.png]]

#### Step 5: Run the script

Now you can run the script in Termux. Your widget should get updated right away.

from: https://glow.li/posts/display-output-of-a-bash-script-on-a-widget/
