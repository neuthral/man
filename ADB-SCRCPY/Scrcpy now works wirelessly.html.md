
# Scrcpy now works wirelessly!


# Wireless

The application communicates with the device over _adb_ , so it should be easy
to make it work wirelessly: [Connect to a device over Wi-
Fi](https://developer.android.com/studio/command-line/adb.html#wireless).

It was not counting on an [adb
bug](https://issuetracker.google.com/issues/37066218) preventing `adb reverse`
to work over a connection established by `adb connect`.

Therefore, we implemented a
[workaround](https://github.com/Genymobile/scrcpy/commit/1038bad3850f18717a048a4d5c0f8110e54ee172)
to fallback using `adb forward` (and reversing the client/server roles) when
`adb reverse` fails.



# How to run scrcpy wirelessly?

Here are the steps:  
1\. Connect the device to the same Wi-Fi as your computer  
2\. Get your device IP address (in Settings → About phone → Status)  
3\. Enable adb over TCP/IP on your device: `adb tcpip 5555`  
4\. Connect to your device: `adb connect DEVICE_IP:5555` (replace `DEVICE_IP`)  
5\. Unplug your device  
6\. Run scrcpy as usual

To switch back to USB mode: `adb usb`.

As expected, the performances are not the same as over USB.

The default scrcpy bit-rate is 8Mbps, which is probably too much for a Wi-Fi
connection. Depending on the use case, decreasing the bit-rate and the
resolution may be a good compromise:

    
    
    scrcpy --bit-rate 2M --max-size 800

For people in a hurry:

    
    
    scrcpy -b2M -m800

Note that while it now works over TCP/IP, this is not an optimal solution for
streaming a video wirelessly, since the raw stream is still sent over TCP,
where a packet loss is very bad for latency, due to [head-of-line
blocking](https://en.wikipedia.org/wiki/Head-of-line_blocking). But it’s
better than nothing!

Under good conditions, it may work pretty well:

On the video, _scrcpy_ is started over USB on the laptop with _Debian_ (on the
right), and over Wi-Fi on the Mac (on the left).

You can now [build, install and
run](https://github.com/Genymobile/scrcpy/blob/master/README.md) the new
version!

[Enjoy!](https://github.com/Genymobile/scrcpy/blob/master/README.md "Enjoy!")
