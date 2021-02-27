## Tested with Firebase February 2021

# gcm.js

tdtsh/gcm.js is forked from [https://github.com/iamyellow/gcm.js](https://github.com/iamyellow/gcm.js)
Thank you iamyellow!

**gcm.js** is an open source module for Titanium Android SDK that lets developers receive GCM push notifications in their Android apps.

Using Google Play Service instead of the fork original gcm.jar

It supports the Titanium SDK 8.5.x

It has a very simple API -almost identical to iOS!- yet flexible and powerful, as it executes Javascript whenever a notification is received, no matter if the app is in foreground or background. More info at:
[Titanium の Android で GCM(Push通知) Google Play Service版 - Qiita 変更する](http://qiita.com/hntn/items/a83072e441ccf4fc715c)

/android/dist/ contains zip with module for Ti SDK 7.0.0+.
 
## build module

> install before android-ndk

```
ti build -p android --build-only
```


## run client example

> install Appcelerator Platform before

> and connect your Android device to PC

```
cd ./example

ti build -p android -T device
```


## run server example

> install node.js before

```
cd ./example_server

npm install

vi demoserver.js
```

> set your API key and Device's RegistrationId

>>>	var GCM = new _GCM('SET YOU API KEY HERE');

>>>	var registration_id = 'SET YOUR DEVICES REGISTRATIONID HERE';


```
node demoserver.js
```



## known issue

- unregister is not implemented

- It does not receive a notification if the application is not started

- Making analytics false in tiapp.xml, https://jira.appcelerator.org/browse/TIMOB-24427


## Forking the module

If you want to fork and compile this module, first rename manifest_template file to manifest.
Then fill the guid (line #16) with a new module uuid with the **uuidgen** command as [this post](http://developer.appcelerator.com/blog/2011/09/module-verification.html) explains.

## Author

jordi domenech, [iamyellow.net](http://iamyellow.net)

## License

Apache License, Version 2.0
