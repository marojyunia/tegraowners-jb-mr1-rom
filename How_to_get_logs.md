# Introduction #

This small how-to will show you how you can get useful log information from your android device.

There are two ways to get log from your device:
  1. Use some terminal app and save logs somewhere on your device (on sdcard for example)
  1. Use adb shell and save logs on your pc. ADB is provided with android sdk which you can get from http://developer.android.com/sdk/index.html

<br>

<h3>How to get logcat</h3>

The Android logging system provides a mechanism for collecting and viewing system debug output. Logs from various applications and portions of the system are collected in a series of circular buffers, which then can be viewed and filtered by the logcat command. You can use logcat from an ADB shell to view the log messages.<br>
<br>
To get logcat on your device you need to do:<br>
<br>
<ol><li>Open terminal app<br>
</li><li>Enter "su" to get root privileges<br>
</li><li>Enter "logcat -f /sdcard/logcat.txt". This will start logcat output to file /sdcard/logcat.txt<br>
</li><li>Stop logcat by "ctrl+c" or just close terminal emulator app</li></ol>

If you use some logcat reader app(for example CatLog), then it should have "save log" option.<br>
<br>
To save logcat with adb shell you need to run "adb logcat > /path/where/save/logcat.txt" from command line on your pc.<br>
<br>
<br>

<h3>How to get kernel log</h3>

Kernel log shows what happens with kernel since tablet power on.<br>
<br>
To get kernel log on your device you need to do:<br>
<br>
<ol><li>Open terminal app<br>
</li><li>Enter "su" to get root privileges<br>
</li><li>Enter "dmesg > /sdcard/dmesg.txt" to save current log. Or run "cat /proc/kmsg > /sdcard/kmsg.txt" to start kernel log output to file.<br>
</li><li>If you are using "cat /proc/kmsg" you need to stop it by "ctrl+c" or close terminal app.</li></ol>

To save kernel log with adb shell you need to run "adb shell dmesg > /path/where/save/dmesg.txt" from command line on your pc.<br>
<br>
<br>

<h3>How to get last_kmsg log</h3>

If your tablet rebooted unexpectedly, you need to save last_kmsg log. It will contain kernel log just before reboot and may show what caused reboot.<br>
<br>
To get last_kmsg log on your device you need to do:<br>
<br>
<ol><li>Open terminal app<br>
</li><li>Enter "su" to get root privileges<br>
</li><li>Enter "cat /proc/last_kmsg > /sdcard/last_kmsg.txt" to save current log.<br>
</li><li>Close terminal app.</li></ol>

To save last_kmsg log with adb shell you need to run "adb shell cat /proc/last_kmsg > /path/where/save/last_kmsg.txt" from command line on your pc.