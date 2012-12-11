## Minifying CSS and JS For Production With Node and Makefiles

- uglifyjs
- cleancss
- how to use a makefile and why make is awesome for its simplicity

here is the makefile from gather

```bash
APPJS = mobile/script/chat.js \
	mobile/script/util.js \
	mobile/script/globalFunctions.js \
	mobile/script/app.js

STYLESHEETS = mobile/stylesheets/normalize.css \
	mobile/stylesheets/fonts.css \
	mobile/stylesheets/vk.css \
	mobile/stylesheets/gather.css \
	mobile/stylesheets/chat.css \
	mobile/stylesheets/sprite.css \
	mobile/stylesheets/leaflet.css

all: 
	cat mobile/script/deps/*.js | uglifyjs -o mobile/script/deps-min.js
	cat $(APPJS) | uglifyjs -o mobile/script/app-min.js
	cat www/script/event-deps/*.js | uglifyjs -o www/script/event-deps-min.js
	cat $(STYLESHEETS) | cleancss -o mobile/stylesheets/styles-min.css 
	glue www/stylesheets/sprite www/stylesheets --retina --algorithm=vertical --namespace=""

debug: 
	cat mobile/script/deps/*.js > mobile/script/deps-min.js
	cat $(APPJS) > mobile/script/app-min.js
	cat www/script/event-deps/*.js > www/script/event-deps-min.js
	cat $(STYLESHEETS) > mobile/stylesheets/styles-min.css
```
  

