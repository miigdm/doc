# RTE enable tables

Adding tables is not encouraged (according to Phat, for the real reasons, ask him) but sometimes it is a good option.

Checking the [tsconfig file](https://github.com/t3kit/theme_t3kit/blob/master/Resources/Private/Extensions/Rtehtmlarea/PageTS/tsconfig.txt) for the RTE we can see at line 24,25 
```
# Uncomment to enable tables in RTE
# showButtons := addToList(insertcharacter, link, table, findreplace, chMode, removeformat, undo, redo, about)
```

Depending what kind of project you have (medium or big) you can either just uncomment the line inside the real tsconfig file or add the line in the pagets of the site as such:

```
RTE.default{
   # Uncomment to enable tables in RTE
    showButtons := addToList(insertcharacter, link, table, findreplace, chMode, removeformat, undo, redo, about)
}
```




