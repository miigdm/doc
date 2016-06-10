# How to edit content elements templates

###Step 1

Create the folder structure in *fileadmin/templates/theme_t3kit* for the new file you want to edit.  
For example, if you want to change the slider, find the original file (from git or within the project) and folder structure:
***theme_t3kit/Resources/Private/Templates/ContentElements/*** 

Inside your new ***/ContentElements/*** folder, create the new slider with the same name as the original filename **"Slider.html"**

Copy the content from the [original file](https://github.com/t3kit/theme_t3kit/blob/master/Resources/Private/Templates/ContentElements/Slider.html) and place it into your new "Slider.html" file. 

###Step 2

Choose **"Template"** in TYPO3 menu.   
Be sure you are on the rootpage.  
Select **"Info/modify"** from the dropdown if it is not already set.  
Click on **"Setup"**

Now you have to create a new templateRoothPath for your new header.  
Add the following typoscript:  
```
lib.fluidContent {
    templateRootPaths {
        2000 =  fileadmin/templates/theme_t3kit/Resources/Private/Templates/ContentElements
    }
 }
```
Save.

The number **2000** is the value we give to the new templateRootPath. By default, 0, 10, 1910, 1911 are already set to the original folder of templateRootPath.  
If you want to make sure that the value you want to use is not already set, you can check it with the **"TypoScript Object Browser"** and find *lib* -> *fluidContent* -> *templateRootPaths* and see what values are already set. 


###Step 3

Now you can start editing your copy of the **"Slider.html"**