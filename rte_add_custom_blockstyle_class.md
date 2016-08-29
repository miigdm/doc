# RTE add custom blockstyle class

####Adding classes to RTE links:

Edit root page, click on the "Resources" tab and in the "Page TSConfig" section add:
```
RTE.classes {
#name of class for html
    two-column{
#name of style in backend
        name = Two columns
    }
}

RTE.default {
#important file to override
contentCSS = fileadmin/templates/theme_t3kit/custom_content_elements/Resources/Public/Extensions/Rtehtmlarea/Css/backend.css

#list allowed classes (must also be defined in the css-file)
    proc.allowedClasses := addToList(two-column)

# A class name to be assigned to the blocks whenever the item is applied to selected text.
    buttons.blockstyle.tags.div.allowedClasses := addToList(two-column)

}

```

The ```"contentCSS = fileadmin/templates/theme_t3kit/custom_content_elements/Resources/Public/Extensions/Rtehtmlarea/Css/backend.css"``` file can be copied from [here](https://github.com/t3kit/theme_t3kit/blob/master/Resources/Public/Extensions/Rtehtmlarea/Css/backend.css). You will also need to create the folder structure as it is written. 
Inside the ```backend.css``` file you need to edit it and add your custom class in the end of the document as such: 

```CSS
div.two-column ,
p.two-column ,
span.two-column  {
  color: #aaa !important;
    -webkit-column-count: 2;
    -moz-column-count: 2;
    column-count: 2;
}
```
and also add the custom css for the actual front end in your custom.less or felayout depending on the project.