# MCH Carousel -- Work in Progress, far from production-ready

## What is MCh Carousel?

Yet another carousel, this time some [obscure developer](https://www.linkedin.com/in/robertogiuntoli) in Barcelona...

It displays any number of pictures in a horizontal strip, with the ability of scrolling left or right. It may also slide pictures automatically.

## Features
* Unlimited number of images [bandwidth and memory permitting...]
* Styled entirely via CSS
* Mobile, keyboard, trackball and mousewheel support
* Each image may be wrapped in a hyperlink
* On-hover image [only on devices with a mouse/trackball]
* Up to 3 lines of caption for each image, each with its own style
* Auto-slide [enabled by default]
* Navigation buttons: slide to beginning, slide left, slide right, slide to end
* Autoslide buttons: pause slide, restart slide
* Support for both left-to-right and right-to-left page flows
* Most options may be changed dynamically, after the carousel has loaded
* Custom jQuery events are emitted for significant visual events

## Sample usage
The following [pseudo] code shows quickly the steps involved in creating an MCh Carousel:
```html
  <!-- first define a container for your images -->
  <div id="whateverIdYouLike">
    <div id="mch-image-list"><!-- this div must have its ID set to mch-image-list -->
      <!-- list the images of your carousel; they will be displayed
             in the same order as they appear here -->
      <img src=... [more properties...]>
      <img src=... [more properties...]>
      [more images...]
    </div>
  </div>
  <!-- the Javascript code to create the carousel is pretty simple -->
  <script type="text/javascript">
    var theCarousel = new MChCarousel( $('#whateverIdYouLike'), 
        // Optionally list here the options that you may
        //   want to use, for example:
        {
            captureArrowKeys: false  // Do not respond to arrow-right nor arrow-left events
        });
  </script>
  </pre>
```
... and here is a fully-fledged [**demo page**](http://www.mesmerizedchild.eu/mch-carousel).

## Dependencies
* [**jQuery 2.1.4**](https://jquery.com/)
* [**jQuery Mouse Wheel Plugin 3.1.13**](https://github.com/jquery/jquery-mousewheel)  
    If you need support for earlier versions of jQuery and/or the jQuery Mouse Wheel Plugin, please let me know.  
    If you have successfully tested [or not!] the carousel with another version of jQuery and/or the mouse-wheel plugin, also let me know.  
    Support for later version of jQuery should be available shortly after they are released.  
    On the other hand, support for jQuery 1.x is out of the question.

## Browser support  
As a rule of thumb, MCh Carousel will work on any browser supported by jQuery 2.1.4 [see [https://jquery.com/browser-support/](https://jquery.com/browser-support/) for more information].  
If you find that your experience is quite different, then let me know.

## FAQ, Good-To-Know and Trivia
* **Is the MCh Carousel responsive?**  
    Being styled using only CSS, as a rule of thumb the MCh Carousel is as responsive as your CSS is.  
    [don't like the next paragraph]  
    The MCh Carousel does attempt to keep the navigation buttons on the screen if the images do not fit into the visible part of its viewport [while hiding those buttons if all images fit into the visible part of its viewport]; in order to achieve this, the MCh Carousel does respond to the window.resize event.  
    However, more-complex events, such as changing the width attribute of an HTML element that contains the carousel, are currently not tracked [wording???] and the navigation buttons might end up in a state inconsistent with the ........... Use the method MChCarousel.forceResize() to force the MCh Carousel to review its state. See the API file [a] for a complete reference.

* **I'm having problems with Google Chrome and other Chromium-based browsers [Opera and UC Browser]; do you know anything about it?**  
    There are two known problems with Chromium that may affect an MCh Carousel:  
  * [scrollLeft() may return incorrect values](https://code.google.com/p/chromium/issues/detail?id=351692); due to this bug, when the zoom level is not at 100%, the autoslide feature will correctly slide all images from the first one to the last the first time, but then it may just halt, instead of automatically sliding back to the first image. The JS code within MCh Carousel tries to cope with this bug, and appears to work around it in a number of scenarios, but your experience might be different... Let me know in case you really come to a dead end, and we can try to figure out a solution.
  * [Lagging scroll](https://code.google.com/p/chromium/issues/detail?id=92812); due to this bug, you may experience lags when sliding; this is particularly visible when the carousel is loaded with large images [scaled down by CSS] and then autoslide slides from the last image back to the first image: the sliding may be choppy. To my knowledge, the only workaround here, is use images that match more closely the size specified by the CSS; contrary to the previous bug, this cannot be worked around in JS code.  

    Neither Firefox nor Internet explorer exhibit the problematic behaviour described above, suggesting that they are indeed rooted in Chromium rather than in MCh Carousel.

* **Under which licence is MCh Carousel released?**
    MIT, see LICENCE.txt ****

* **Who is the author?**  
    The author is an Italian guy enjoying life in Barcelona, and who recently embarked on the adventure of web development.  
    The fact that [as of August 2015] he's still fairly new to this business does not automatically imply that he's a total noob, as he's been around in the IT industry since 1988.  
    His mission is to deliver quality products, and thus tends to test thoroughly his software before releasing it.  
    He also believes that cooperation is key in any endavour, so please do send suggestions, ideas, [constructive] criticism, kudos and anything else, to his email address: [rg@mesmerizedchild.eu](mailto:rg@mesmerizedchild.eu).  

## Th-Th-Th-Th-That's All Folks!
...and **Thank You** for your interest!
