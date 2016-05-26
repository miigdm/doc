# Custom Special Menu templates

## Introduction

Recent versions of TYPO3 (including T3kit) are using the "Fluid Styled Content"-extension. The biggest difference compared to using "CSS Styled Content" is that it's Fluid-driven instead of Typoscript-driven. One of the things this extension provides are Special Menus that you can use for creating sitemaps, a menu of selected pages and more.

![](menu_type.png)

If you'd like to create a new type of Special Menu that doesn't already exist, here is how.

##Create a new Menu Type
1. Choose a partial-template you want to use (from the original extension) as your starting point and copy it to fileadmin. You can locate the original id by inspecting the drop-down in back-end. In this case we want to use "Menu of sub-pages of selected pages" as a starting point, which is value 1.![](locate_id.png)

2. Locate and copy this file (Type-1.html) from: ```typo3/sysext/fluid_styled_content/Resources/Private/Partials/Menu/``` to for example: ```fileadmin/templates/theme_t3kit/fluid_styled_content/Resources/Private/Partials/Menu/``` and rename it to an unique number, for example: Type-99.html

3. Edit this file to do whatever you want it to do.

4. Add these lines to your Page TSConfig. Use the same number as point 2 and choose a describing name:

 ```
# Add menu
TCEFORM.tt_content.menu_type {
   types {
      menu{
         addItems {
            99 = Menu of selected pages with image
         }
      }
   }
}```

5. Last step, add this to your Typoscript setup and make sure "1920" is a unique number.

 ```
# Include custom menu
lib.fluidContent.partialRootPaths.1920 = fileadmin/templates/theme_t3kit/fluid_styled_content/Resources/Private/Partials/
```

6. Now you will be able to select your Special Menu from the Menu Type-dropdown.

