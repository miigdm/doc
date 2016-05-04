# Custom News templates

## Introduction
We have our own custom news templates in theme_t3kit extending the original from the News extension.
* Timeline grouped in years
* List view. 
* Cards. 

#### Changing templates 

You can switch between the different views by editing the *News system plugin* here
![](newstemplate)


## How to add new templates
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
Bubbles = News as bubbles
```






