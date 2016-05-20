# RootFiles


Folder [copyToRoot](http://realfavicongenerator.net/faq#.Vz7QlpOLQUE) consist of several important files which we should copy to root of our site. Almost all of them are icons for browsers and different devices. [Please read good explanation how to work with this icons.](http://realfavicongenerator.net/faq#.Vz7QlpOLQUE) Our choice is not use all possible icons, but also not only favicon.ico. We found something like golden middle.  

####Workflow:
**Designer:**  
* Prepare file icon.png (260px/260px)  

**FE developer:**  
* Generate all icons using [this web service](http://realfavicongenerator.net/) from icon.png. Use recomended settings.
* Needed meta tags already added on the site ```templates/parts/head.hbs```


```html
<link rel="icon" type="image/png" href="/favicon-196x196.png" sizes="196x196">
<link rel="icon" type="image/png" href="/favicon-16x16.png" sizes="16x16">
<link rel="icon" type="image/png" href="/favicon-32x32.png" sizes="32x32">
<meta name="msapplication-TileColor" content="#00a300">
<meta name="msapplication-TileImage" content="/mstile-144x144.png">
```
* Only if we need we should change title color on this meta tag:
   ```html
<meta name="msapplication-TileColor" content="#9f00a7">
```
  * Change it on ```templates/parts/head.hbs``` file, and then on ```t3layout``` extension. (variable ```msTileColor```).  
* Save generated archive with icons, and copy needed files to folder ```copyToRoot``` of our project.
  * apple-touch-icon.png
  * browserconfig.xml
  * favicon-16x16.png
  * favicon-196x196.png
  * favicon-32x32.png
  * favicon.ico
  * mstile-144x144.png
  * mstile-150x150.png
  * mstile-310x150.png
  * mstile-310x310.png
  * mstile-70x70.png
* Last step is to copy files from folder ```copyToRoot``` to the root of **TYPO3** installation.

####humans.txt
* Also good to have [humans.txt](http://humanstxt.org/) file. It is just a way to have more information about the authors of the site. It is not important.