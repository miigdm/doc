# t3kit project types


Project Types:  
* Basic  
* Medium  
* Big  



###Basic
Budget: 35-**80** hours   
Project type: Waterfall  
Start: 1-2 month  
Hosting: shared hosting  

Simple website. Design and architecture is based on t3kit out of the box. Main part of design should be implemented based on **t3kit Customizer** or Theme variables in TYPO3 BE. ( http://t3kit.github.io/theme_t3kit_customizer )  
* Additional css styling could be added to *fileadmin/custom/css/* (**custom.less** or **custom.css**)  
* Additional js scripts could be added to *fileadmin/custom/js/custom.js*  
* Can't change templates/partials/layouts.  
* Can't create new BE layouts and templates.  
* Can't create new content elements.  
* Can't install new extensions.  
* **PageTS** and **TypoScript** could be added in TYPO3 BE or additional files in *fileadmin/templates/Configuration/*  
* Site based on **theme_t3kit** extension + **felayout_t3kit** as a submodule 

---

###Medium
Budget: **80-250** hours   
Project type: Waterfall  
Start: 2-3 month  
Hosting: shared or dedicated hosting  

Websites with design that have some specific features/changes compare to t3kit base.

* Possible to install **new extensions. ** 
* Possible to create new custom content elements (*fileadmin/*)  
  * Not more than 5 new custom elements.  
* Possible to change and create new  BE layouts/templates/partials/layouts (fileadmin/)   
  * Not more than 7 rewritings of existed *partials/templates/layouts*  
  * Not more than 2 new BE layouts  
* **PageTS** and **TypoScript** could be added in TYPO3 BE or additional files in *fileadmin/templates/Configuration/* folder  
* Site based on **theme_t3kit** extension.  
* New Front-End layout or t3kit Front-End layout with additional css styling (custom.css)  
  * In this type of project we are able to use [three types of FE layout](https://pixelant.gitbooks.io/doc/content/three_types_of_felayout_for_medium_and_big_project.html) based on our needs and design.  

---

###BIG
Budget: **250+** hours   
Project type: Waterfall or Agile  
Start: 3+ month  
Hosting: dedicated hosting   

Big and design heavy websites using just main t3kit features and patterns. A lot of custom features and functions.

* Possible to install new extensions.  
* New t3kit sub-theme extension:  theme_t3kit_projectName (based on theme_t3kit).  
* New Front-End layout: felayout_customer_projectName (*fileadmin/*).



---



###Three types of FE layout  

Every new medium or big project require a new Front End layout. There is three ways of using felayout depending on project needs:  

* felayout CSS - providing css for TYPO3.  
Typical way of working with felayout, like it was on CORE. Providing css, js, icons, fonts and images for TYPO3 installation. Need to create new felayout_customer_projectName.


* felayout LESS - providing less for TYPO3.  
Type of felayout that provide less files for TYPO3 installations. Developing and supporting will be more complicated, but in this case we are able to change css variables from TYPO3 BE (Theme constants). Need to create new felayout_customer_projectName.

* Updatable felayout (using felayout_t3kit)  
Not many changes in design compared to default t3kit layout. Style with custom.less/custom.css, basically like basic site. The style changes will be committed to main repository, so changes are trackable.


