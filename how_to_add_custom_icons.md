# How to add custom icons
####Generating of new set of icons

Open `selection.json` file in [IcoMoon](https://icomoon.io/) app. Edit/add custom icons. 

![](custom-icons.png)

After editing - select custom icons to add them to set. 

Press `Generate font` and download it with configuration:
  - Font name: `icons`
  - Class prefix: `icon-`


####Placing set of icons
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

####Adding TCE configs with new icon set (f.e. for bigIconTextButton element)
After placing icon files we can add them to elements, for example - for `bigIconTextButton`. For this we need to edit start page: `Page → Home → Edit → Resources (tab)`

Add these lines to `Page TSConfig`
```
TCEFORM.tt_content.pi_flexform.bigIconTextButton.sDEF.iconClass {
    config {
        cssFile = fileadmin/custom/icons/style.css
    }
}
```

To add the new icons to Page Properties (under the Appearance tab), add these lines to `Page TSConfig`
```
TCEFORM.pages.tx_themes_icon.iconClass {
    config {
        cssFile = fileadmin/custom/icons/style.css
    }
}
```

####Adding new set of icons to FE
First you have to make a copy of  `style.css` for front-end. Please call it `style_fe.css`.

Edit this file and remove this section:

```css
[class^="icon-"], [class*=" icon-"] {
    /* use !important to prevent issues with browser extensions that change fonts */
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
```
Otherwise it will conflict with elements like Icon, Text and Button, which uses the class `icon-text-btn`).

Then, to add these icons to FE we need to include them to `/fileadmin/custom/css/custom.less`. 

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
@import url('../icons/style_fe.css');
```


