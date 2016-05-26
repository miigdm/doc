# Custom Special Menu templates #

## Introduction ##

t3kit and recent versions of TYPO3 are using the "Fluid Styled Content"-extension instead of "CSS Styled Content". The biggest difference being that it is Fluid-driven instead of Typoscript-driven (with performance gains). One of the things this extension provides are Special Menus that you can use for creating sitemaps, a menu of selected pages and more.

![](menu_type.png)

If you'd like to create a new type of Special Menu that doesn't already exist, here is how.

##Create a new Menu Type##
Choose a partial-template you want to use (from the original extension) as your starting point and copy it to fileadmin. You can locate the original id by inspecting the drop-down in back-end. In this case we want to use "Menu of sub-pages of selected pages" as a starting point, which is value 1.

![](locate_id.png)

Locate and copy this file (Type-1.html) from: ```typo3/sysext/fluid_styled_content/Resources/Private/Partials/Menu/``` to for example: ```fileadmin/templates/theme_t3kit/fluid_styled_content/Resources/Private/Partials/Menu/``` and rename it to an unique number, for example: Type-99.html

Edit this file to do whatever you want it to do.

Page TSConfig:

Add these lines (with the corresponding number, 99, like before) and choose a describing name:




