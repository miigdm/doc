# Design
##Instructions for Designers

---

###Design
* Please before starting new design, check this site [FElayout_ricky](http://felayout_ricky.testserver.pixelant.nu/) . This site structure created special for understanding which templates and content element we have already implemented. It is like a puzzles. Always keep in mind all these content elements before start new design.

###Responsive design
* Large display view
* Desktop view
* Tablet view
* Mobile viev
* In Pixelant Core we use only two variants of design ```(Mobile < 992px & Desktop > 992px)```
  * **Note**: Better to start design from mobile view. ```(Mobile first)```

###PSD
* Use Bootstrap grid in PSD files
* Use Notes and Layer compositions to include comments and mouse over stuff in PSD files
* Blend mode in photoshop: only normal. Without: multiply, screen, overlay etc. And without opacity in gradients. In general opacity not very good.
* Layer should be alone, without creating additional layers for special effect
* Understandable layer structure.


###Fonts
* If we want use unusual fonts, better to use Google Fonts. But always keep in mind not all fonts have good view on Windows especially in big sizes.
* Not more two - three additional web fonts, and in general not more five fonts(with OS standart fonts)


###Icons
Pixelant Core use a lot of icons. Our choice is icon font (a font with icons as its glyphs). We use web-service [icomoon](https://icomoon.io/) to generate icon font with needed icons. We can use unique icons for every project, even for small project.  

**Workflow for Designers:**  

* Open [icomoon.io](https://icomoon.io/), add needed icon libraries and select icons which we need for this project. Also always should remember about required icons for Pixelant Core.
* Save and download selected icons (fonts and png). Use recommended settings. Only change font name to icons.
* For design in Photoshop use ```png``` icons.
* Prepare files for FE developers (archive from Icomoon ```icons.zip```)
  * **Important**: Select as few as possible icons from Icomoon. Only icons which we will use on our project.


###Favicon
* Prepare file icon.png ```(260px/260px)```.
  * Note: It should be simple icon, with possibility to scale and pretty good view in different sizes. [Read more about whole process with favicons.](https://pixelant.gitbooks.io/doc/content/rootfiles.html)


###Files
* PSD files with design. (Several files, depend on how many responsive points we have)
* Instructions for fonts.
* icons.zip (icomoon.io)
* icon.png (260px/260px) (favicon)
* High Resolution logo with transparency (png, svg)
* Additional images

###Links
* Animations:
  * [Animate.css](http://daneden.github.io/animate.css/)
  * [Hover](http://ianlunn.github.io/Hover/)
  * [PageTransitions](http://tympanus.net/Development/PageTransitions/)
  * [Effeckt](http://h5bp.github.io/Effeckt.css/#0)
* Fonts:
  * [Google Fonts](https://www.google.com/fonts/)
  * [Typekit](https://typekit.com/)
  * [Typetester](https://www.typetester.org/)
  * [Somadesign](http://somadesign.ca/demos/better-google-fonts/)
  * [Webfonts Ampersands](http://hail2u.github.io/google-webfonts-ampersands.html)
  * [Cssfontstack](http://www.cssfontstack.com/)
  * [Typecast](http://typecast.com/preview/google)
  * [Brick](http://brick.im/)

###Required Icons for Pixelant Core

```html
<span class="icons icon-t3-mobile"></span>
<span class="icons icon-t3-mail"></span>
<span class="icons icon-t3-home"></span>
<span class="icons icon-t3-sitemap"></span>
<span class="icons icon-t3-login"></span>
<span class="icons icon-t3-dropdown-arrow"></span>
<span class="icons icon-t3-search"></span>
<span class="icons icon-t3-map"></span>
```
####Social icons

```html
<span class="icons icon-t3-facebook"></span>
<span class="icons icon-t3-twitter"></span>
<span class="icons icon-t3-linkedin"></span>
<span class="icons icon-t3-vimeo"></span>
<span class="icons icon-t3-googleplus"></span>
<span class="icons icon-t3-pinterest"></span>
```
####Carousel
```html
<span class="icons icon-t3-slider-arrow-left"></span>
<span class="icons icon-t3-slider-arrow-right"></span>
```
####Quote
```html
<span class="icons icon-t3-quoteMark"></span>
```
####Files
```html
<span class="icons icon-t3-file"></span>
<span class="icons icon-t3-film"></span>
<span class="icons icon-t3-picture"></span>
```
####News
```html
<span class="icons icon-t3-newsCarousel-arrow-up"></span>
<span class="icons icon-t3-newsCarousel-arrow-down"></span>
<span class="icons icon-t3-news-categoryIcon"></span>
<span class="icons icon-t3-news-archiveIcon"></span>
```
####Search
```html
<span class="icons icon-t3-search-pagination-left"></span>
<span class="icons icon-t3-search-pagination-right"></span>
```