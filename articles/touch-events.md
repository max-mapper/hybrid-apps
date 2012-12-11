# Using Touch Events To Make Web Apps Feel Fast

## author notes

build on https://github.com/maxogden/blog/blob/master/posts/fast-webview-applications.html#L101-L122 and https://github.com/maxogden/blog/blob/master/posts/fast-webview-applications.html#L151-L179 but demonstrate usage of the newer https://github.com/ftlabs/fastclick instead of masseuse.js

<h1 id="touch-events">Touch Events</h1>

In mobile browsers and WebViews there is a (roughly) 300ms delay on all `click` events (this includes the `mouse` events like `onmousedown`). This is for capturing certain gestures like double tap to zoom in, since you have to wait a little bit to see if the user is going to single tap or double tap. Since we are in a viewport controlled non-zoomable application container we don't actually want this behavior but sadly there is no easy way to disable this and make clicks fast again.

```html
<video preload="none" poster="hybrid-apps/tree/master/media/slowclick.jpg" controls>
  <source src="hybrid-apps/tree/master/media/slowclick.m4v">
    <source src="hybrid-apps/tree/master/media/slowclick.ogv">
</video>
```

Luckily [`touch`](https://developer.mozilla.org/en-US/docs/DOM/TouchEvent) events have no artificial delay. The problem is that click events have hardcoded behavior in them (like if you click on a link it takes your browser to the href in that link) whereas touch events have no default behavior. To switch out clicks for touches you have to first ignore all clicks on the page and then tell the browser to listen for touches but treat them exactly like it would clicks. In 2011 an engineer at Google wrote about a solution they developed called the <a href="https://developers.google.com/mobile/articles/fast_buttons">fast button</a> but only published a single post and not an easy to use open source project.

There is a project by the [Financial Times Labs](http://labs.ft.com/) called [Fast Click](https://github.com/ftlabs/fastclick) that is well maintained and provides a nice implementation of the Google-style fast button approach.
