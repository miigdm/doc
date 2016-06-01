# How to add new layout content wrappers

Adding a layout wrapper will add a class that wraps the content element of your choosing. This can be helpful when you want an element to look different from the original element. 

**Step 1.** Find the elements pagets and setupts files (located in ```theme_t3kit/Configuration/ContentElements/```)  you want to add a layout wrapper to.  
For this example we will use the "Quote" elements [pagets](https://github.com/t3kit/theme_t3kit/blob/master/Configuration/ContentElements/Quote.pagets) and [setupts](https://github.com/t3kit/theme_t3kit/blob/master/Configuration/ContentElements/Quote.setupts).  

**Step 2.** Inside the pagets file we will find a section that is commented out with a set of instruction:
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

**Step 3.** Edit the root page of your site
