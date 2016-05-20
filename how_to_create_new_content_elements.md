# How to create new content elements

This process simplifies the steps of creating new content elements, as it auto-generates most of the files/folders we need.


####Step 1

1. Edit rootpage  
1. Click on the "**Resources**" tab
1. In TypoScript Configuration there is "**Available Items**".   
1. Find: "**EXT:theme_t3kit :: Enable Custom Content Elements (fileadmin/templates/...) (theme_t3kit)**" and click it. It should now appear in the "**Selected Items**" box.

Save.

####Step 2
1. Choose "**Template**" from the TYPO3 menu.   
1. Choose rootpage.
1. The dropdown should have "**Info/Modify**" selected.  
1. Click on "**Edit the whole template record**"
1. Click on "**Includes**" tabs.  
1. In the "Available Items", find "**EXT:theme_t3kit :: Enable Custom Content Elements (fileadmin/templates/...) (theme_t3kit)**" and click it.  
1. Check in the "**Selected Items**" that the "**EXT:theme_t3kit :: Enable Custom Content Elements (fileadmin/templates/...) (theme_t3kit)**" is there now.

Save. 


---


You will now have a new tab called "**Custom elements**" when creating elements, with your new content element: ![](content element.png)
In the "**Fileadmin**", there will now be new created folders and files:
(**fileadmin/templates/theme_t3kit/custom_content_elements/**)



```
.
|____Configuration
| |____Backend
| | |____ext_tables.php
| |____FlexForms
| | |____flexform_twbsButton.xml
| |____PageTS
| | |____twbsButton.pagets
| | |____WizardTabs.pagets
| |____TCA
| | |____Overrides
| | | |____tt_content.php
| |____TypoScript
| | |____twbsButton.setupts
|____Resources
| |____Private
| | |____Language
| | | |____CustomContentElements.xlf
| | |____Templates
| | | |____CustomContentElements
| | | | |____TwbsButton.html
| |____Public
| | |____Backend
| | | |____Icons
| | | | |____CustomContentElements
| | | | | |____customElement.svg```

A brief explanation of the files:

**Configuration folder:**  
- ```ext_tables.php  ```  
 - This file is for the icon of the element in backend. Without it, there will be a broken icon.
 - Add new iconRegistry here
 - **Not unique** per content element (shared).
    

- ```flexform_twbsButton.xml ```
  - This file is optional if you know that your element needs custom settings, which can not be handled original fields in tt_content. 
  - Should not be used for anything that will be rendered on page. 
  - **Unique** per content element
  

- ```twbsButton.pagets ```
  - This file is to get the content available in new content wizard tab. 
  - It can also be used to manipulate flexform and form values. 
  - **Unique** per content element


- ```WizardTabs.pagets```  
  - This is only for adding the tab in backend for new elements wizard. 
  
 
- ```tt_content.php ```
  - This file is used to configure what fields that are available in backend form. 
  -  Also adds Content element type selector. 
  -  Also where the type icon is set. 
  -  If a flexform is created, you will register it here. 
  -  **Not unique** per content element (shared)


- ```twbsButton.setupts```
  - This file is for configurating how to render the content. 
  - **Unique** per content element


**Resources folder:**

- ```CustomContentElements.xlf```
  - This file is for the descriptions of the element 
  -  **Not unique** per content element (shared)


- ```TwbsButton.html```
  - This file is the actual template for the element
  - **Unique** per content element


- ```customElement.svg```
  - This file is the icon for the element
  - This file could be unique or you could link your new content to this file.









