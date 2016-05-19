# Pixelant Manual

##Pixelant Code Performance Guide  
###Frontend Workflow



---


###Site performance

* Use PageSpeed Insights  and Pagespeed Optimization to check site’s performance.
* Enable Compression (GZip).  
* Include resources from different domains (subdomains) to provide parallel loading.  
* Omit the protocol portion (http:, https:) from URLs pointing resources
```html
<!-- Not recommended -->
<script src="http://www.google.com/js/gweb/analytics/autotrack.js"></script>
<!-- Recommended -->
<script src="//www.google.com/js/gweb/analytics/autotrack.js"></script>
```



---

###Javascript

* Combine multiple js files into one  
* Minify JavaScript  
  * [UglifyJS](http://lisperator.net/uglifyjs/)   
  * [YUI Compressor ](http://yui.github.io/yuicompressor/)  
* Use JsHint & JSCS  
* https://docs.google.com/a/pixelant.se/document/d/11306kuBBpjFNw0TOZaCCRgm8aHiLJ-WatGcksuFHA4o/edit?usp=sharing  
* Put external scripts after external stylesheets if possible. (better, at the bottom of the **body** tag)  
* Don't use little js scripts (~ 10 lines) in external files (use inline scripts)
* Move the inline scripts after CSS files  
* Use CDN for external scripts if possible (eg google CDN  ) https://developers.google.com/speed/libraries/  
* Defer loading for not very important js scripts (eg third-party scripts for ads, analytics, social widgets, etc)  

---

###CSS

* Stylesheets should always be specified in the head of a document  
* Combine multiple external CSS files into one  
* Minify CSS  
  * [Clean-css](https://github.com/GoalSmashers/clean-css)   
  * [YUI Compressor](http://yui.github.io/yuicompressor/)   
* Remove unused CSS
* https://github.com/giakki/uncss
* CSS Lint 
* https://docs.google.com/a/pixelant.se/document/d/1iZjusxcbNtEfJHkBX9Q5hWXkGzRTjPcJGOyJf19h9wI/edit?usp=sharing
* Don't use little css styles (~20 - 50 lines) in external files (use inline css styles)
* Put external stylesheets before external scripts if possible
* Always Use normal CSS property names with vendor-prefixed ones
* Use css animations instead of js animations



---

###Images

* Supporting

| Format | Transparency | Animation | Browser |
| -- | -- | -- | -- |
| GIF | Yes | Yes | All |
| PNG | Yes | No | All |
| JPEG | No | No | All |
| SVG | Yes | Yes | All |
| JPEG XR | Yes | Yes | IE |
| WebP | Yes | Yes | Chrome, Opera, Android |

* Use optimal format for images:


