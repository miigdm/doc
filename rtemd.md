# RTE add custom class
####Adding classes to RTE links:

Edit root page, click on the "Resources" tab and in the "Page TSConfig" section add:



1*:
```RTE.default.proc.allowedClasses := addToList(btn-greenborder)```

2*:
 ```RTE.default.buttons.link.properties.class.allowedClasses := addToList(btn-greenborder)```

3*: ```RTE.classes.btn-greenborder.name = Button with green border```


1* : This is to add the classes you want to the link

2*: This is to add it to the list

3*: This is the name that will show up in the dropdown

It is also possible to add multiple classes. Then it would look like this:


```
RTE.default.proc.allowedClasses := addToList(btn-blueborder, btn-greenborder)
RTE.default.buttons.link.properties.class.allowedClasses := addToList(btn-blueborder, btn-greenborder)

RTE.classes.btn-blueborder.name = Button with blue border
RTE.classes.btn-greenborder.name = Button with green green border
```


Save the added script.

---
####Adding classes to text style:

Edit root page, click on the "Resources" tab and in the "Page TSConfig" section add:

```
RTE.classes {
        
    name-of-class{
    	name = name shown in backend
    	}
}

RTE.default {

    contentCSS = filepath in filelist

    # list allowed classes (must also be defined in the css-file)
    proc.allowedClasses := addToList(name-of-class)

    # A class name to be assigned to the blocks whenever the item is applied to selected text.
    buttons.blockstyle.tags.div.allowedClasses := addToList(name-of-class)

    ## for the textstyle
    buttons.textstyle.tags.span.allowedClasses := addToList(name-of-class)

}
```

The "contentCSS = filepath in filelist" is important because, without it, the new text style with not be visible in backend. You will need to [copy the original ](https://github.com/t3kit/theme_t3kit/blob/master/Resources/Public/Extensions/Rtehtmlarea/Css/backend.css)and place it somewhere in filelist, add typoscript for the new location in setupts, then add your own css for the new class. For example:
```
div.name-of-class ,
p.name-of-class ,
span.name-of-class  {
  color: #137486 !important;
  font-size: 18px;
}
```