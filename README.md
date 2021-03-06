# jQuery Turbolinks

Do you like [Turbolinks](https://github.com/rails/turbolinks)? It's easy and fast way to improve user experience of surfing on your website.

But if you have a large codebase with lots of `$(el).bind(...)` Turbolinks will surprise you. Most part of your JavaScripts will stop working in usual way. It's because the nodes on which you bind events no longer exist.

I wrote jquery.turbolinks to solve this problem in [my project](http://amplifr.com). It's easy to use: just require it *after* `jquery.js` and `tubrolinks.js`, but before other scripts.

Sponsored by [Evil Martians](http://evilmartians.com/).

This project is a member of the [OSS Manifesto](http://ossmanifesto.org/).

## Usage

Gemfile:
``` js
gem 'jquery-turbolinks'
```

JavaScript manifest file:
``` js
//= require jquery.turbolinks
```

And it just works!

## `$.setReadyEvent`

By default [ready](https://github.com/kossnocorp/jquery.turbolinks/blob/master/src/jquery.turbolinks.coffee#L17:L18) function is binded to [page:load](https://github.com/rails/turbolinks/#events) event.

If you want to change it use `$.setReadyEvent` function:

``` js
$.setReadyEvent('page:change');
```

## `$.setFetchEvent`

By default right after trigger `page:fetch` `$.isReady` is set to false. And after `page:load` is set to true.

If you want to change default behaviour you can use `$.setFetchEvent`:

``` js
$.setReadyEvent('custom_loading_event');
```

# Changelog

This project uses [Semantic Versioning](http://semver.org/) for release numbering.

## 1.0.0-rc1 (November 28, 2012)

* Set $.isReady to false after `page:fetch` [#6](https://github.com/kossnocorp/jquery.turbolinks/issues/6);
* add `$.setFetchEvent` function;
* remove all delegated events after trigger fetch event [#8](https://github.com/kossnocorp/jquery.turbolinks/issues/8).

## 1.0.0-rc (November 8, 2012)

* Add turbolinks as dependency (kudos to [@gbchaosmaster](https://github.com/gbchaosmaster));
* run callback after adding to waiting list if `$.isReady` [#6](https://github.com/kossnocorp/jquery.turbolinks/issues/6).

## 0.2.1 (October 15, 2012)

* Pass jQuery object to each callback [#4](https://github.com/kossnocorp/jquery.turbolinks/issues/4)

## 0.2.0 (October 10, 2012)

* Change event: `page:change` -> `page:load` (kudos to [@davydotcom](https://github.com/davydotcom));
* added ability to change ready event via `$.setReadyEvent`

## 0.1.0 (October 3, 2012)

* First, initial release

# Contributors

Idea and code by [@kossnocorp](http://koss.nocorp.me/).

# [The MIT License](https://github.com/kossnocorp/jquery.turbolinks/blob/master/LICENSE.md)
