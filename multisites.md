# Multisites

# -Under construction-#
**Guidelines**: 

**What is acceptable:** 
* Several small sites  
* Medium sites with original theme_t3kit and theme_t3kit_bluemountain
	* Uses shared felayout for each theme  
* Medium sites with original theme_t3kit and a big project with its own theme  
	* Uses shared felayout for each theme 
* Favicons can be stored in fileadmin/favicons/nameOfProject


**What is *not* acceptable:**  
* Usage of different types of felayout for sites using the same theme  
* 

**What to think about:** 
* Will there be new elements on each site?  
* Will they share the same design?  
* Will they not share the same design?  
* Will they share same design but have different new elements on each site? 
* The root template site should always be empty from information about the companies 
* Take into consideration about what types of elements share the same styling classes. If you want to make changes to an element in "Site 1" remember that the same element on "Site 2" will be effected. 
* Temporary URL should be *.maincompanyname.typo3konsult.se
	* For example: companyname1.maincompanyname.typo3konsult.se
* Favicons

**Pros & Cons:**  
Pros:
* Editors can change content for multiple sites.

Cons:  
* Clearing cache will apply to all sites 

---

Same type of felayout is always shared between sites.  
**Exception:** additional theme inside installation (t3kit_bluemountain/t3kit_projectname), then all sites which use bluemountain, will have the same felayout.

Use cases:

* **felayout_upgradable** 	= original inside theme_t3kit, changes from theme variables and/or custom.css
* **felayout_css** 		= felayout_css
* **felayout_less** 		= felayout_less

**Use case #1  **  
Multisite with **only basic** sites:  
* Styling changes are made to the variables from "Theme" in TYPO3 menu for each respective site (Or using the theme_t3kit_customizer and copy pasting the changes into setupts).
* They all share the same theme_t3kit/felayout and is upgradable.  
 
```
Theme_t3kit(felayout_upgradable)  
	|  
	|-Site 1 (basic) - felayout_upgradable  
	|  
	|-Site 2 (basic) - felayout_upgradable   
	|  
	|-Site 3 (basic) - felayout_upgradable   
```


**Use case #2 ** 
 
Multisite with **only medium** sites.
* Styling changes are made from the felayout.  
* **Important**: Take into consideration about what types of elements share the same styling classes. If you want to make changes to an element in "Site 1" remember that the same element on "Site 2" will be effected.  

```
Theme_t3kit(felayout_upgradable)
	|
	|-Site 1 (Medium) - felayout_css 
	|
	|-Site 2 (Medium) - felayout_css 
```



**Use case #3.**  
Multisite with **only medium** sites.
* Styling changes are made from the felayout.  
* Possibility add new variables to use from the "Theme" in TYPO3 menu.
* **Important**:  Take into consideration about what types of elements share the same styling classes. If you want to make changes to an element in "Site 1" remember that the same element on "Site 2" will be effected.

```
Theme_t3kit(felayout_upgradable)
	|
	|-Site 1 (Medium) - felayout_less 
	|
	|-Site 2 (Medium) - felayout_less 
	|
	|-Site 3 (Medium) - felayout_less 
```





**Use case #4. **   
Multisite with **only medium** sites.
* Styling changes are made to the variables from "Theme" in TYPO3 menu for each respective site (Or using the theme_t3kit_customizer and copy pasting the changes into setupts). And using custom.less/custom.css. 
* Possibilities: 
  * Original custom.less/custom.css is shared for all sites, then including other custom_sitename.less/custom_sitename.css that overrides the original custom.less/custom.css
* **Important**: Take into consideration about what types of elements share the same styling classes. If you want to make changes to an element in "Site 1" remember that the same element on "Site 2" will be effected. 

```
Theme_t3kit(felayout_upgradable)
	|
	|-Site 1 (Medium) - felayout_upgradable  
	|
	|-Site 2 (Medium) - felayout_upgradable 
	|
	|-Site 3 (Medium) - felayout_upgradable 
``` 




**Use case #5.**  
Multisite with **medium sites, different themes.**  
Styling changes are made from the felayout (Site 1, 2, 5).  
Styling changes are made from the felayout (Site 3, 4).  
```
Theme_t3kit(felayout_upgradable)
	|
	|-Site 1 (Medium) - felayout_css
	|
	|-Site 2 (Medium) - felayout_css
	|
	|--Theme_t3kit_bluemountain (felayout_upgradable_bluemountain)
	|	|
	|	|-Site 3 (Medium) - felayout_css_2 (seperate from Site 1, 2, 5 but shared with Site 4)
	|	|
	|	|-Site 4 (Medium) - felayout_css_2 (seperate from Site 1, 2, 5 but shared with Site 3)
	|
	|-Site 5 (Medium) - felayout_css 
    ```




**Use case #6**  
Multisite with **medium sites and big.**  
Styling changes are made from the felayout (Site 1, 2, 4).  
Styling changes are made from the felayout (Site 3).  
```
Theme_t3kit(felayout0)
	|
	|-Site 1 (Medium) - felayout_less 
	|
	|-Site 2 (Medium) - felayout_less 
	|
	-
Theme_t3kit_projectname (felayout_less/felayout_css)
	-	|
	|	|
	|	|-Site 3 (Big) - felayout_less/felayout_css
	|
	|-Site 4 (Medium) - felayout_less 
```
**Use case #7**  
Multisite with **big.**  
 
```
Theme_t3kit_projectname(felayout_less/felayout_css)
	|
	|-Site 1 (Big) - felayout_less/felayout_css  
	|
	|-Site 2 (Big) - felayout_less/felayout_css 
	|
	|-Site 3 (Big) - felayout_less/felayout_css 
```