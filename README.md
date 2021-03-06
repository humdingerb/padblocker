# PadBlocker
PadBlocker is a Haiku input_server filter to block the touchpad while you're typing.

Most OSs have drivers for laptops which will allow the automatic dismissal of mouse-down events while typing. Haiku is not one of them (yet).

### To install manually (not from a hpkg package)
Copy PadBlocker to _~/config/non-packaged/add-ons/input_server/filters_).

### To change sensitivity
The first time the filter is run, it will make a default settings file in _~/config/settings_ named "_PadBlocker_settings_". This is just a text file, containing a number representing in milliseconds (1/1000 secs) the delay between when the last key-up message is handled and when the next mouse-down message will be allowed.   
You can set this number to whatever you want, but I imagine anything more than 500 (half a second) would be counter-productive.

Since the threshold is loaded on instantiation of the filter (i.e. when the input_server is fired up) any changes you make won't be noticed until the server is restarted, manually, or on reboot.   
To restart the input_server manually, open the Terminal and type:

_/system/servers/input_server -q_

The mouse and keyboard will go dead for a second or two as the input server restarts, and the add-ons are loaded. Poof. You're good to go.

### Thanks
PadBlocker was created originally by Shamyl Zakariya in 2000 for the BeOS under the name "TouchpadInputServerFilter".   
He thanks to Magnus Landahl for writing his superb Be Debug Console without which he would not have been able to verify that this thing actually worked or not (it does).
