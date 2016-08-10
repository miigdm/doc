# How to add custom icons

Open `selection.json` file in [IcoMoon](https://icomoon.io/) app. Edit/add custom icons. 

![](custom-icons.png)

After editing - select custom icons to add them to set. 

Press `Generate font` and download it with configuration:
  - Font name: `icons`
  - Class prefix: `icon-`
  
Unzip IcoMoon archive and place all content (some of the content can be omitted) to `/fileadmin/custom/icons`

Structure of the `/fileadmin/custom/icons` folder:
```
  ├──demo-files (optional)
  |  ├──demo.css
  |  └──demo.js
  |
  ├──fonts
  |  ├──icons.eot
  |  ├──icons.svg
  |  ├──icons.ttf
  |  └──icons.woff
  |
  ├──Read Me.txt (optional)
  ├──demo.html (optional)
  ├──selection.json
  └──style.css
```

After placing icon files we can add them to elements, for example - for `bigIconTextButton`. For this we need to edit start page: `Page → Home → Edit → Resources (tab)`

Add this lines to `Page TSConfig`
```
TCEFORM.tt_content.pi_flexform.bigIconTextButton.sDEF.iconClass {
    config {
        cssFile = fileadmin/custom/icons/style.css
    }
}
```

To add this icons to FE we need to include them to `/fileadmin/custom/css/custom.less`:

```css
/* Icons mixin */
.icons {
	font-family: 'icons' !important;
    speak: none;
    font-style: normal;
    font-weight: normal;
    font-variant: normal;
    text-transform: none;
    line-height: 1;

    /* Better Font Rendering =========== */
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
}

/* Importing new icons set */
@import url('../icons/style.css');
```


