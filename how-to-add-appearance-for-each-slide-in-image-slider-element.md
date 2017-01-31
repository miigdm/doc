# How to add appearance for each slide in Image Slider Element

With slide appearance, we will add a special class for every slide in Image Slider Element.  This can be helpful when we want a slide to look different from the another slide.

**Step 1.**
Find the `Slider.pagets` and `Slider.setupts` files (located in [```theme_t3kit/Configuration/ContentElements/```](https://github.com/t3kit/theme_t3kit/tree/master/Configuration/ContentElements))


**Step 2.**
Inside the [pagets](https://github.com/t3kit/theme_t3kit/blob/master/Configuration/ContentElements/Slider.pagets) file we will find a section that is commented out with a set of instruction:
```
# # This is for adding options in the selectbox in each slide.
# TCEFORM.sys_file_reference.tx_themet3kit_slide_appearance {
#      addItems {
#          --div-- = Slider slide appearances:
#          10 = Light text and right aligned text area
#          20 = Dark text and centered aligned text area
#     }
# }
```
So we just need to uncomment it and change a name of appearance how we need. After this, we will have the slide appearance visible in the backend for every slide.

**Step 3.**
Next, we need to add the classes for every appearance which we added in the previous step.
Open the [setupts](https://github.com/t3kit/theme_t3kit/blob/master/Configuration/ContentElements/Slider.setupts) file, where we will find a section that is also commented.
```
# appearance {
# # Extend appearance for each slide for this element
#   10 = example-class
#   20 = example-class
# }
```
Now we need to uncomment this section and add class mappings for every slide appearance.