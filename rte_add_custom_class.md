# RTE add custom class
Adding classes to RTE links:

Edit root page, click on the "Resources" tab and in the "Page TSConfig" section add:


---


1*:
```RTE.default.proc.allowedClasses := addToList(btn-greenborder)```

2*:
 ```RTE.default.buttons.link.properties.class.allowedClasses := addToList(btn-greenborder)```

3*: ```RTE.classes.btn-greenborder.name = Button with green border```



---
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


