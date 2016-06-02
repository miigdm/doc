# How to add new appearance content wrappers

Adding a appearance content wrapper will wrap the class of the content element. This can be helpful when you want an element to look different from the original element.

The procedure is almost the same as adding a new [layout content wrapper](https://pixelant.gitbooks.io/doc/content/how_to_add_new_layout_content_wrappers.html) but with some small changes.

**Step 1.** Find the elements pagets and setupts files (located in [```theme_t3kit/Configuration/ContentElements/```](https://github.com/t3kit/theme_t3kit/tree/master/Configuration/ContentElements))  you want to add a appearance wrapper to.  
For this example we will use the "Table" elements [pagets](https://github.com/t3kit/theme_t3kit/blob/master/Configuration/ContentElements/Quote.pagets) and [setupts](https://github.com/t3kit/theme_t3kit/blob/master/Configuration/ContentElements/Quote.setupts).  

**Step 2.** Inside the [pagets](https://github.com/t3kit/theme_t3kit/blob/master/Configuration/ContentElements/Quote.pagets) file we will find a section that is commented out with a set of instruction:
```
# # Use layout field to customize Layout select-box on quote
# # extend layout select-box only for this element
# TCEFORM.tt_content.layout {
#     types {
#         quote {
#             addItems {
#                 --div-- = Quote layouts:
#                 # add value with index 0, to set it as a default, only for this element
#                 0 = Default layout for this element
#                 11 = Example layout only for quote
#             }
#         }
#     }
# }
```
Copy this block of text.

**Step 3.**  
Edit rootpage of your site   
Click on the "Resources" tab  
In TypoScript Configuration there is "Page TSConfig".  
Here you will add the copied block of text and remove the "#" from each row.  
Remove the ```0 = Default layout for this element``` and ```11 = Example layout only for quote```  and we need to find a number that is not occupied already.

**Step 4.**  
Duplicate your browser tab and choose "Template" from the TYPO3 menu.  
Choose rootpage.  
The dropdown should have "Typoscript Object Browser" selected.  
Navigate to ```tt_content.quote.dataProcessing.1910.classMappings``` in the tree. 