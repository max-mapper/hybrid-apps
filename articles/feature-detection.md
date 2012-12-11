## Cross-Platform Mobile Code Via Feature Detection

html copy/paste from a previous article I wrote:

<h1 id="cross-platform">Cross-platform code</h1>
<p>
  On app load we first execute all of the common, platform independent JS and then do a bit of UA sniffing (using zeptos <code>$.os</code> plugin) to load browser + platform specific scripts. These scripts include things like the required <code>cordova.js</code> library (which at the time of this writing has specific builds for specific platforms), our phonegap plugin JS files, and any browser specific polyfills. We also have a iOS specific stylesheet that currently has a single line to enable <code>-webkit-transform</code> animations (they are disabled by default because Android animation performance is abysmal).
</p>
<p>
  There are a few other places in the app where we have platform specific code. Here is a snippet from our date picker code that executes after you choose a date or time (or both) in the native date picker UI popup dialog:
</p>
<pre><code data-language="javascript">
if ($.os.ios) {
  $('.datepicker').text(moment(start).format("MMM Do h:mma"))          
} else {
  $('.datepicker').text(moment(start).format("MMM Do"))
  $('.timepicker').text(moment(start).format("h:mma"))
}
</code></pre>
<p>