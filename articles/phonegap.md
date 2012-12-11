## Using Phonegap To Deploy Web Apps As Native

target audience: beginners

common misconceptions about phonegap:

- it doesn't implement its own browser, it just uses the platform provided webview
- it doesn't provide any UI -- you have to write your own web app UI
- native plugins have to be implemented on each platform

the following is from a previous article I wrote about @gather:

The majority of the app was written on my laptop in Chrome + its dev tools, the same workflow I've been using for years. Our designer, Michael Felix (@objcts) worked with us during the initial conceptual phase and then starting whipping up some pixel perfect PSDs.

On device testing is a must. Get a new Android + iPhone and an old Android and iPhone. We went with the Galaxy Nexus, iPhone 4S, some random LG android phone that runs 2.3 and an iPhone 3GS. Turns out nobody has really complained to us about iPhone 4.x compatibility so we are currently iOS5+6 only. Android emulators are a waste of time, just plug your device in. iPhone Simulator is nice though. With PhoneGap nowadays you can do pretty much everything from the command line:

      
      // get phonegap
      git clone https://github.com/apache/incubator-cordova-ios.git
      cd incubator-cordova-ios

      // create a new XCode project
      ./bin/create ~/src/gather-ios com.gather.gather Gather
      cd ~/src/gather-ios
      
      // compile app
      ./cordova/build
      
      // run in simulator
      ./cordova/emulate
      
      // get an .ipa for ad-hoc (testflight) or app store distribution
      gem install shenzhen && ipa build
      
or for Android:
      
      // get phonegap
      git clone https://github.com/apache/incubator-cordova-android.git
      cd incubator-cordova-android

      // create a new Eclipse project
      ./bin/create ~/src/gather-android com.gather.gather Gather
      cd ~/src/gather-android
      
      // generate an .apk and run it on a plugged in phone
      ./cordova/BOOM
