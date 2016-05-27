# Multisites

#Under construction#

**Important to think about before setting up multisite installation:**  
Will there be new elements on each sites?  
Will they share the same design?  
Will they not share the same design?  
Will they share same design but have different new elements on each site?  
How many hours for each site?

---

Same kind of felayout is always shared.
	Exception: other theme inside installation (t3kit_bluemountain/t3kit_projecname), then all sites which use bluemountain, will have the same felayout.

Use cases (These are only use cases and not how real life works):

* felayout0 (original) 	= original inside theme_t3kit, changes from theme variables and/or custom.css
* felayout1 (css) 		= felayout_css
* felayout2 (less) 		= felayout_less
* felayout3 (big) 		= felayout_less/felayout_css


Use case #1
```
Theme_t3kit(felayout0)  
	|  
	|-Site 1 (basic) - felayout0   
	|  
	|-Site 2 (basic) - felayout0   
	|  
	|-Site 3 (basic) - felayout0   
```

Multisite with only basic sites:  
* Styling changes are made to the variables from "Theme" in TYPO3 menu for each respective site (Or using the theme_t3kit_customizer and copy pasting the changes into setupts).
* They all share the same theme_t3kit/felayout and is upgradable. 

Use case #2
```
Theme_t3kit(felayout0)
	|
	|-Site 1 (Medium) - felayout1 shared
	|
	|-Site 2 (Medium) - felayout1 shared
```
 
Multisite with only medium sites.  
* Styling changes are made from the felayout.  
* **Important**: Take into consideration about what types of elements share the same styling classes. If you want to make changes to an element in "Site 1" remember that the same element on "Site 2" will be effected. 


Use case #3.  
```
Theme_t3kit(felayout0)
	|
	|-Site 1 (Medium) - felayout2 shared 
	|
	|-Site 2 (Medium) - felayout2 shared
	|
	|-Site 3 (Medium) - felayout2 shared
```

Multisite with only medium sites.
* Styling changes are made from the felayout. Possibility add variables for each seperate site to use from the "Theme" in TYPO3 menu.
* **Important**:  Take into consideration about what types of elements share the same styling classes. If you want to make changes to an element in "Site 1" remember that the same element on "Site 2" will be effected.  



Use case #4.  
Theme_t3kit(felayout0)
	|
	|-Site 1 (Medium) - felayout0 shared 
	|
	|-Site 2 (Medium) - felayout0 shared
	|
	|-Site 3 (Medium) - felayout0 shared
Multisite with only medium sites.
Styling changes are made to the variables from "Theme" in TYPO3 menu for each respective site (Or using the theme_t3kit_customizer and copy pasting the changes into setupts). And using custom.less/custom.css. 
	- Possibilities: 
		Original custom.less/custom.css is shared for all sites, then including other custom_sitename.less/custom_sitename.css that overrides the original custom.less/custom.css
	- Important: 
		Take into consideration about what types of elements share the same styling classes. If you want to make changes to an element in "Site 1" remember that the same element on "Site 2" will be effected.  




#5.
Theme_t3kit(felayout0)
	|
	|-Site 1 (Medium) - felayout1 shared
	|
	|-Site 2 (Medium) - felayout1 shared
	|
	|--Theme_t3kit_bluemountain (felayout0-1)
	|	|
	|	|-Site 3 (Medium) - felayout1-1 (seperate from Site 1, 2, 5 but shared with Site 4)
	|	|
	|	|-Site 4 (Medium) - felayout1-1 (seperate from Site 1, 2, 5 but shared with Site 3)
	|
	|-Site 5 (Medium) - felayout1 shared
Multisite with medium sites, different themes.
Styling changes are made from the felayout (Site 1, 2, 5).
Styling changes are made from the felayout (Site 3, 4).



#6.
Theme_t3kit(felayout0)
	|
	|-Site 1 (Medium) - felayout2 shared 
	|
	|-Site 2 (Medium) - felayout2 shared
	|
	-
Theme_t3kit_projectname (felayout3)
	-	|
	|	|
	|	|-Site 3 (Big) - felayout3
	|
	|-Site 4 (Medium) - felayout2 shared
Multisite with medium sites and big.
Styling changes are made from the felayout (Site 1, 2, 4).
Styling changes are made from the felayout (Site 3).
