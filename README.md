#unveil.js
###A very lightweight plugin to lazy load images for jQuery or Zepto.js



Most of us are familiar with the [Lazy Load](http://www.appelsiini.net/projects/lazyload) plugin by [Mika Tuupola](http://www.appelsiini.net/).
This plugin is very useful and it boosts performance delaying loading of images in long web pages because images outside of viewport (visible part of web page) won't be loaded until the user scrolls to them.
Lazy Load has some cool options such as custom effects, container, events or data attribute. If you're not gonna use any of them you can reduce the file size by leaving just the essential code to show the images.
That's what I did and this is my lightweight version of Lazy Load with support for serving high-resolution images to devices with retina displays - less than 1k.

Visit unveil's [project page](http://luis-almeida.github.com/unveil/) to read the documentation and see the demo.


###Browser support
Compatible with All Browsers and IE7+.


###License
Unveil is licensed under the [MIT license](http://opensource.org/licenses/MIT).


## Versioned entry points

The root plugin and demo retain the existing jQuery/Zepto API. The historical v2 and v3 implementations are available separately:

| Variant | Script | API | Demo |
| --- | --- | --- | --- |
| Existing jQuery/Zepto | [jquery.unveil.js](jquery.unveil.js) | `$("img").unveil(threshold, callback)` | [Current demo](index.html) |
| v2 work in progress | [versions/v2/jquery.unveil.js](versions/v2/jquery.unveil.js) | `$("img").unveil(options)` | [v2 demo](versions/v2/index.html) |
| v3 vanilla JavaScript | [versions/v3/unveil.js](versions/v3/unveil.js) | `var lookup = new Unveil("img", threshold, callback)` | [v3 demo](versions/v3/index.html) |

- **v2:** Options are `threshold` (default `0`), `container` (a jQuery/Zepto collection; default window), `debounce` (milliseconds; default `0`), and `custom` (skip automatic source assignment). It uses the `unveil` event and emits `unveiled` after automatic source assignment; the positional callback API is absent. See the [entrance animation](versions/v2/demo/entrance_animations.html) and [screen-size selection](versions/v2/demo/screen_size.html) examples.
- **v3:** The `Unveil` implementation needs no jQuery. It returns a `lookup` function for manual checks and calls the callback with the image as `this`. Scroll/resize checks use a fixed 200 ms delay. Its demo retains the historical supporting scripts and image assets.
- Select one jQuery entry point per page: the root and v2 plugins both define `$.fn.unveil`. The browser-support statement above describes the root plugin; the vanilla variant uses native `querySelectorAll` and `addEventListener`.

The alternate scripts and demos preserve the [v2 branch snapshot](https://github.com/pointclickreality/unveil/commit/0635b56c3703c9758004571109d716d296e3ed65) and [v3 branch snapshot](https://github.com/pointclickreality/unveil/commit/d8da036cbac240fe506bf8b7c616b358f777dd64). Historical external demo resources are retained.
