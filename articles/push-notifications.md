## Adding Push Notifications To Android/iOS PhoneGap App

- apple TLS gateway API
- google GCM HTTPS+JSON API
- example using node
- how to make dev + prod certs to use with the node apn module
- when to use a hosted push provider like urban airship
- phonegap plugins that you'll need

from a previous article I wrote:

<p>
  Push notifications are one of the biggest reasons we aren't a web app. There are some nice plugins for both <a href="https://github.com/phonegap/phonegap-plugins/tree/master/iOS/PushNotification">iOS</a> and <a href="https://github.com/marknutter/GCM-Cordova">Android</a> to handle registering devices for push notifications and getting device tokens than you can send to your server and use to send push notifications later. At the moment the APIs are different between the two platforms but there is some work happening now to standardize the JS API for registering a device and receiving a push notification across all platforms that offer push notification functionality. There is a plugin for Android called StatusBarNotification that lets you send messages to display in the Android status bar (as pictured below on the left). The JS API <a href="https://github.com/phonegap/phonegap-plugins/blob/master/Android/StatusBarNotification/statusbarnotification.js#L61-133">actually polyfills</a> the <a href="http://www.w3.org/TR/notifications/">Web Notification API</a> from the W3C, which is a big win for future proofing our app.
</p>
<p><img src="/media/pushnotifications.png"></p>