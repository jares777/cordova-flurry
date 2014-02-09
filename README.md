cordova-flurry
==============

Allow integration with [Flurry Analytics](http://www.flurry.com/) in your mobile apps developed using Apache Cordova.

It is available for Android and iOS.

Target
-------

- Apache Cordova >= 3.0
- Platforms: Android & iOS
- Flurry Analytics SDK (Android: 3.3.0 / iOS: 4.3.2)


Installation
-------

To install the plugin, use the Cordova CLI and enter the following:<br />
`cordova plugin add https://github.com/Initsogar/cordova-flurry`

###- Specific instructions for Android

Add the following code in your main activity.

```
  @Override
  protected void onStart()
  {
    super.onStart();
    FlurryAgent.onStartSession(this, "YOUR_API_KEY");
  }

  @Override
  protected void onStop()
  {
    super.onStop();
    FlurryAgent.onEndSession(this);
  }
```

You'll need to import FlurryAgent class using:<br />
`import com.flurry.android.FlurryAgent;`

###- Specific instructions for iOS
Add the following code inside your didFinishLaunchingWithOptions method in your AppDelegate.m
```
  [Flurry startSession:@"YOUR_API_KEY"];
```
Remember to replace YOUR_API_KEY with your own key.


Basic Usage
-------
To log an event use:<br />
` window.plugins.flurry.logEvent('EVENT_NAME');`

Credits
-------

https://github.com/jfpsf/flurry-phonegap-plugin
