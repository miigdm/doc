# Icons

**Pixelant Core** use a lot of icons. Our choise is icon font (*a font with icons as its glyphs*). We use web-service [icomoon](https://icomoon.io/) to generate icon font with needed icons. We can use unique icons for every project, even for small project.  

####Workflow:
**Designer:**  

* Open [icomoon.io](https://icomoon.io/), add needed icon libraries and select icons which we need for this project. Also always should remember about required icons for Pixelant Core.
* Save and download selected icons (fonts and png). Use recomended settings. Only change font name to icons.
* For design in Photoshop use png icons.
* Prepare files for FE developers (archive from Icomoon ```icons.zip```, and PSD file with design)
  * **Important**: Select as few as possible icons from Icomoon. Only icons which we will use on our project.  
  
**FE developer:**  
* Open web application [Icomoon](https://icomoon.io/), and import ```selection.json``` from ```icons.zip```. Then push button ```font``` and you will see icons and special code near every icon.
* Open ```icons.less``` file and find **RESERVED ICONS**. Then change ```content``` for every icon according to new icons (*special code*).
* For all others icons you can create special classes, or add them in css files if you can't change templates.  

**Add in css (less):**  
```less
.your-class:before{
    .icons(); //mixin
    content: "\e607";
}
```

**Special classes:** 
 ```css
.icon-image:before {
    content: "\e600";
}
.icon-image2:before {
    content: "\e601";
}
.icon-play:before {
    content: "\e602";
}
```
  * **Note**: Then use these classes in HTML using this construction ```<span class="icons icon-image"></span>```


---


####Required icons for Pixelant Core
Pixelant Core use several reserved icons. It means that in Pixelant template we use constructions with predefined classes ```<span class="icons icon-type"></span>```. We can change icons in this classes. Open file ```icons.less``` and change ```content``` for every icon according to new icons.  

**RESERVED ICONS**

```less
// =======================================
// == RESERVED ICONS for t3layout_ricky===
// =======================================
.icon-t3-mobile:before {content: "\32";}
.icon-t3-mail:before {content: "\35";}
.icon-t3-home:before {content: "\53";}
.icon-t3-sitemap:before {content: "\eb";}
.icon-t3-login:before {content: "\3f";}
.icon-t3-dropdown-arrow:before {content: "\ff";}
.icon-t3-search:before {content: "\55";}
.icon-t3-map:before {content: "\44";}

//Social icons
.icon-t3-facebook:before {content: "\128";}
.icon-t3-twitter:before {content: "\126";}
.icon-t3-linkedin:before {content: "\131";}
.icon-t3-vimeo:before {content: "\124";}
.icon-t3-googleplus:before {content: "\12b";}
.icon-t3-pinterest:before {content: "\12d";}

//Carousel
.icon-t3-slider-arrow-left:before {content: "\fe";}
.icon-t3-slider-arrow-right:before {content: "\101";}

//Quote
.icon-t3-quoteMark:before {content: "\fe";}

//Files
.icon-t3-file:before {content: "\e605";}
.icon-t3-film:before {content: "\e603";}
.icon-t3-picture:before {content: "\e600";}

//News
.icon-t3-newsCarousel-arrow-up:before {content: "\100";}
.icon-t3-newsCarousel-arrow-down:before {content: "\ff";}
.icon-t3-news-categoryIcon:before {content: "\e607";}
.icon-t3-news-archiveIcon:before {content: "\e609";}

//Search
.icon-t3-search-pagination-left:before {content: "\fe";}
.icon-t3-search-pagination-right:before {content: "\101";}
```