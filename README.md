#Dante Editor

####Just another Medium editor clone.

##Motivation:

I´ve tried all the medium clones out there, they are really great and all have it´s pros & cons, [but none of them have all the features that medium wysywig provides](http://howtox.com/medium-editor-clones-in-js/), so I wonder, how difficult could be build my own Medium clone?

## Demo:

[http://michelson.github.io/Dante/](http://michelson.github.io/Dante/)

Until now I´ve been able to implement the following features:

## Features:

+ HTML sanitizer for pasted or loaded text.
+ Image upload for paste events.
+ Image upload for legacy images of existing images.
+ The medium (+) Tooltip to embed or upload media.
+ Tab navigation.
+ Embeds:
  + Image Uploader with *preview* and caption option.
  + Embed data for pasted link through OEmbed services.
  + Embed media information for pasted links through OEmbed services.
+ CSS tries to use the same fonts used in Medium, (if you have already setup those fonts) or fallbacks to open fonts (by Google fonts) or system fonts.
  + serif: freight-text-pro fallbacks to Merriweather or Georgia,
  + sans:  jaf-bernino-sans fallbacks to Open Sans or Lucida Grande


## Usage:

### HTML:

```html
  <div id="editor">
    your content here
  </div>
```

### Javascript:

```html
  <script type="text/javascript">
    editor = new Dante.Editor(
      {
        el: "#editor",
        upload_url: "/images.json", //it expect an url string in response like /your/server/image.jpg or http://app.com/images/image.jpg
        store_url: "/save" //post to save

      }
    );
    editor.start()
  </script>
```

### Configuration options:

    el:          default: #editor
    debugMode:   default: false
    upload_url:  default: /uploads.json
    oembed_url:  default: http://api.embed.ly/1/oembed?url="
    extract_url: default: http://api.embed.ly/1/extract?url="
    store_url:   url to store data with interval , defaults to none
    store_interval: default: 15000 (15 secs)
    spellcheck:  default: false
    default_loading_placeholder: image placeholder to show when uploaded/pasted images are loading , defaults to a grey background

### Rails / AssetPippeline

in Gemfile

```gem "dante-editor"```

### stylesheets:

```@import "dante";```

### javascripts:

```//= require 'dante'```

## Disclaimer:

This Library will work fine on latest versions of Chrome/Safari/FF/IE.
We don't have any intention to target all browsers versions, really... if you like this library and you need backward compatibility with an specific version you can submit a patch to help with the development or just upgrade your shitty browser :D

**BTW , this library is an official beta release, so there are known bugs that we are currently working on.
see TODO list below.**

## Dependencies:

Some dependencies are required in order to Dante editor works properly:

+ Jquery
+ [Underscore](https://github.com/documentcloud/underscore)
+ [Sanitize.js](https://github.com/gbirke/sanitize.js)


**Drop underscore and jquery dependencies are on our roadmap.**


## Development:

There is a web app for development to work with the source files and make the proper tests. To use application:

### Installation:

+ install ruby
+ execute `bundle install`

### Start app:

`bundle exec rackup config.ru` and visit http://localhost:9292

or

`bundle exec middleman ` (this is without upload server)
and visit localhost:4567

or

`foreman start` and visit http://localhost:9292

### Tests:

tests are located in source/tests and /source/assets/spec folder and accessible by visit host/tests

## TODO

  [read todo](./TODO.md)

## MAINTAINERS:

+ [Miguel Michelson](http://github.com/michelson)
+ [Cristian Ferrari](http://github.com/cristianferrarig)

### Alternatives:

+ https://github.com/sofish/pen
+ https://github.com/orthes/medium-editor-insert-plugin


### LICENSE

[Licensed under MIT.](./license.md) 2014