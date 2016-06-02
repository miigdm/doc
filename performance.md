# Performance

###Frontend Code Performance Guide


---

####JavaScript
* Combine multiple **js** files into one
* Minify JavaScript:
  * [UglifyJS](http://lisperator.net/uglifyjs/)
  * [YUI Compressor](http://yui.github.io/yuicompressor/)
* Use **JsHint & JSCS**
* Put external scripts after external stylesheets if possible. (*better, at the bottom of the body tag*)
* Don't use little js scripts (*~ 10 lines*) in external files (use **inline** scripts)
* Move the inline scripts after CSS files.
* Defer loading for not very important js scripts (eg third-party scripts for ads, social widgets, etc)


#### CSS
* Stylesheets should always be specified in the ```head``` of a document.
* Combine multiple external **CSS** files into one.
* Minify **CSS**
  * [Clean-css](https://github.com/giakki/uncss)
  * [YUI Compressor](http://yui.github.io/yuicompressor/)
* Remove [unused CSS](https://github.com/giakki/uncss)
* [CSS Lint](https://github.com/CSSLint/csslint)
* Don't use little css styles (*~20 - 50 lines*) in external files (use inline css styles)
* Put external stylesheets before external scripts if possible.
* Always Use normal CSS property names with vendor-prefixed ones.
* Use **css animations** instead of **js animations**

#### Images
* Use optimal format for images:
  * Photos - **JPEG, PNG-24**
  * Simple image (few colours) (eg logos) - **GIF, PNG-8**
  * Simple image with transparency - **GIF, PNG-8**
  * High complexity images with transparency - **PNG-24**
  * Line art - **SVG**
* Use ```save for web``` in photoshop, when you save image for website.
* Compress images:
  * [Jpegtran](http://jpegclub.org/jpegtran/)
  * [Gifsicle](http://www.lcdf.org/gifsicle/)
  * [PngQuant](https://pngquant.org/)
  * [OptiPng](http://optipng.sourceforge.net/)
* Use **css sprites**
* Use **Data-URI**
* Use **css** instead **images** if possible. [One Div](http://one-div.com/)
* Do not use **BMPs** or **TIFFs**.
* Use unicode symbols in **html** or **css** instead images if possible:
  * [Unicode-table](http://unicode-table.com/en/)
  * [Unicode support](http://unicode.johnholtripley.co.uk/)
  * [Unicode character recognition](http://shapecatcher.com/)
* Use special fonts (*with icons*) instead images if possible.
* Build Custom Fonts
  * [Icomoon](https://icomoon.io/)
