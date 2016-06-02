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

