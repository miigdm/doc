# How to add new appearance column wrappers

Adding a wrapper to the column can be helpful when you want the it to look different from the original columns styling.

In this example we will be adding wrappers to all the advanced column grids.

**Step 1.** Find the "```AdvancecColumnGrid```" [pagets](https://github.com/t3kit/theme_t3kit/blob/master/Configuration/GridElements/PageTS/AdvColumnGrid.pagets) file (located in [```theme_t3kit/Configuration/GridElements/PageTS/```](https://github.com/t3kit/theme_t3kit/blob/master/Configuration/GridElements/PageTS/)).  

**Step 2.** Inside the [pagets](https://github.com/t3kit/theme_t3kit/blob/master/Configuration/ContentElements/Quote.pagets) file we will find a section that we will need:
```
# Add a wrapper to Gridelements
# Items in "wrapper" select box will appear in all grid elements on the site.
TCEFORM.tt_content.wrapper {
   types {
       gridelements_pi1 {
           # Based on that the default items still exists.
           addItems {
                --div-- = Gridelements wrappers:
                11 = Example Gridelements wrapper 1
                12 = Example Gridelements wrapper 2
                13 = Footer bottom row wrapper
           }
       }
   }
}
```
Copy this block of text.

**Step 3.**  
Edit rootpage of your site   
Click on the "Resources" tab  
In TypoScript Configuration there is "Page TSConfig".    
Here you will add the copied block of text.  
Remove this part: 
```
11 = Example Gridelements wrapper 1
12 = Example Gridelements wrapper 2
13 = Footer bottom row wrapper
```
And we need to find a number that is not occupied already.

**Step 4.**  
Duplicate your browser tab and choose "Template" from the TYPO3 menu.  
Choose rootpage.  
The dropdown should have "Typoscript Object Browser" selected.  
Navigate to ```tt_content.gridelements_pi1.20.10.setup.Adv1ColumnGrid.cObject.dataProcessing.365.classMappings``` in the tree. ![](Screenshot at jun 02 13-08-03.png)

Here we find that 11,12,13,100,101,102 are occupied, so we can not use these.

**Step 5.**  
Go back to the previous browser tab and add a number of your choosing with the name of your choosing.
It should look something like this now:
```
# Add a wrapper to Gridelements
# Items in "wrapper" select box will appear in all grid elements on the site.
TCEFORM.tt_content.wrapper {
   types {
       gridelements_pi1 {
           # Based on that the default items still exists.
           addItems {
                --div-- = Gridelements wrappers:
                99 = Light-Gray background
           }
       }
   }
}
```
Now that we have added the new item, we need to add it to the four different AdvancedColumnGrids. Add this underneath the text we just wrote:
```
TCEFORM.tt_content.pi_flexform.gridelements_pi1.columns.column_1_content_wrapper < TCEFORM.tt_content.pi_flexform.gridelements_pi1.columns.column_content_wrapper_definition
TCEFORM.tt_content.pi_flexform.gridelements_pi1.columns.column_2_content_wrapper < TCEFORM.tt_content.pi_flexform.gridelements_pi1.columns.column_content_wrapper_definition
TCEFORM.tt_content.pi_flexform.gridelements_pi1.columns.column_3_content_wrapper < TCEFORM.tt_content.pi_flexform.gridelements_pi1.columns.column_content_wrapper_definition
TCEFORM.tt_content.pi_flexform.gridelements_pi1.columns.column_4_content_wrapper < TCEFORM.tt_content.pi_flexform.gridelements_pi1.columns.column_content_wrapper_definition
```
Save.

**Step 6.**  
Now we need to add the class to the wrapper.  

Choose "Template" from the TYPO3 menu.  
Choose rootpage.  
The dropdown should have "Info/Modify" selected.  
Click on "Setup".  
Add the block of text:
```
tt_content.gridelements_pi1.20.10.setup.Adv1ColumnGrid.cObject.dataProcessing.365.classMappings {
    99 = light-gray-bg
}
tt_content.gridelements_pi1.20.10.setup.Adv2ColumnGrid.cObject.dataProcessing.365.classMappings {
    99 = light-gray-bg
}
tt_content.gridelements_pi1.20.10.setup.Adv3ColumnGrid.cObject.dataProcessing.365.classMappings {
    99 = light-gray-bg
}
tt_content.gridelements_pi1.20.10.setup.Adv4ColumnGrid.cObject.dataProcessing.365.classMappings {
    99 = light-gray-bg
}
```

Save.