## When To Use PhoneGap Native Plugins

- plugins that provide their own native UI elements are difficult because you have to overlay the native UI on top of the webview UI
- in gather I treat native UI components as modal popups
- there are also native plugins you can use to polyfill web browsers, such as using socketrocket to polyfill websockets on iOS

from a previous article I wrote:
"We use native plugins to do only a few things: popup browsers for the OAuth login dance, date + time pickers for forms and push notifications. Our entire UI is just one big web view."
