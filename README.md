# Multitouch Community
Issue and feature request tracking for the [Multitouch](https://multitouch.app) app

Go to the [Issues](https://github.com/rxhanson/Multitouch-Bugs/issues) tab to post bugs, feature requests, or questions.

Feel free to comment on any existing feature requests that you also want to request. The more requests, the more likely I'll do it.

If you're filing a bug, please include the following:
* MacOS version
* Multitouch version
* Detailed steps to reproduce

If you wish to contact me directly, feel free to send an email to support@multitouch.app

## Troubleshooting FAQ

#### The app stops recognizing gestures when my mac wakes from sleep and I have to restart the app.
If this happens, go to the settings tab and check the box for "Restart on wake" and this restart will happen automatically.
This isn't the default behavior because it typically just makes it longer for gestures to be available when waking from sleep, and not everyone has this issue.

#### The app stops recognizing gestures randomly after a while. When I restart the app, it works again. 
Not all macs are the same, so the solution to this can vary. Here's some things to try.
* Only run one "Gesture" app at a time (don't run alongside BTT).
* Disable "Restart on wake" if you don't experience the issue above.
* Restart your mac.
* Try enabling "Avoid private framework" in the settings tab. The private framework is 100% necessary for Magic Mouse gestures, but trackpad gestures can function without it. By enabling this setting, the Magic Mouse will still use the private framework but the trackpad will not. For some users, avoiding the private framework is better, for some users, it's worse.
