# weechat

![[Pasted image 20230726110302.png]]

I figured out how to have WeeChat in [Termux](https://termux.com/) create a notification on your android device whenever someone mentions your username or you receive a private message.

You need to have [Termux:API](https://play.google.com/store/apps/details?id=com.termux.api) installed for this. `All` you need to do is type following command into WeeChat:

```sh
	/set trigger.trigger.beep.command "/print -beep;/exec -bg termux-notification -t 'IRC Notification' -c "${tg_tag_nick}: ${tg_message_nocolor}";/exec -bg termux-vibrate"
```

#### Explanation

Normal WeeChat behavior is to send a BEL character to the terminal whenever someone mentions you or sends you a private message. This extends that with the commands termux-notification and termux-vibrate found in the [Termux:API](https://play.google.com/store/apps/details?id=com.termux.api). The content of the notification is ${tg_tag_nick} (which is the user who sent you the message) and ${tg_message_nocolor} (which is the message without coloring). [Here](https://weechat.org/files/doc/devel/weechat_user.en.html#trigger_data_print) you can find more available variables.

# profanity

![[Pasted image 20230726110521.png]]

Just [like with weechat](https://glow.li/posts/using-pixel-fonts-in-a-browser-without-font-smoothing/) you can now receive Android notifications on [Termux](https://termux.com) when you receive a message in [Profanity](https://profanity-im.github.io/). I wrote a small plugin to achive exactly that. You can download it from [GitHub](https://github.com/Neo-Oli/profanity-termux-notification) and install it with `/plugins install ./profanity-termux-notification/termuxnotify.py`. Read more about the installation requirements and configuration options on [GitHub](https://github.com/Neo-Oli/profanity-termux-notification).



from: https://glow.li

