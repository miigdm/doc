# Custom News templates

## Introduction

We have our own custom news templates in theme_t3kit extending the original from the News extension.

**Timeline**  News shown as a timeline grouped and divided in years.
The timeline also has some javascript functionality for opening the news when clicked. This javascript can be found in felayout_t3kit.

**Listview** 
News shows as listview.

**Cards** 
News shown as cards.


There is also a custom style for the single view in news.


#### Changing templates 

You can switch between the different views by editing the *News system plugin* here
![](newstemplate)


## How to add a new template
To add new custom templates for News create your file in:  
*theme_t3kit/Resources/Private/Extensions/News/Partials/List/*

To add the custom template to the dropdown in News plugin open the file located here: 
*theme_t3kit/Resources/Private/Extensions/News/Typoscript/PageTS/tsconfig.txt*

Here you will find:
 ```
tx_news.templateLayouts {
        Timeline = News with timeline
        Cards  = News as Cards
        ListView = News as List
}```

Here you will have to add your new template. It is important that the typoscript declaration has the same name as the filename. E.g if you create a new template called Bubbles.html you should add the below in the typoscript: 
```
Bubbles = News as fluffy bubbles
```



## Dependencies  
[dotdotdot.js](http://dotdotdot.frebsite.nl/) - To maintain the same layout on the news elements the Cards and Listview templates use this js library to truncate text.

[felayout_t3kit](https://github.com/t3kit/felayout_t3kit/) - CSS and JS.

