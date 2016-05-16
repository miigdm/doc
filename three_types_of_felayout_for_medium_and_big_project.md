# Three types of felayout for medium and big projects

Every new medium or big project require a new Front End layout. There is three ways of using felayout depending on project needs.  
* felayout css
* felayout less
* updatable felayout


### felayout CSS - providing css for TYPO3.  
Standard way of working with felayout, like it was on CORE. Providing css, js, icons, fonts and images for TYPO3 installation.

**Installation:**  
```mkdir felayout_projectname```  
```cd felayout_projectname ```   
```yo fe-kit``` (make sure that you read about Pixelant Front-End Starter Kit)

**Front-End Developing:**  
Run ```grunt``` to start static server with livereload localhost:9004  
Run ```grunt +css``` to start static server [same as **grunt**] plus it generates all Front-End service files plus CSS styling for CMS needs, and copy it to **css** folder. [with livereload]  
Run ```grunt pushCss``` to compile all Front-End service files plus CSS styling for CMS needs, copy it to separate branch css and push to remote git server.  
Run ```grunt check``` to check HTML/CSS/JS files according project code conventions

**t3kit settings** (TYPO3 BE -> Theme constants -> Expert):  
FElayout type = css  
Path to felayout = fileadmin/felayout_projectname


NOTE: If you are working with **t3kit vagrant machine** on your local, you can use both sites for development, TYPO3 on **localhost:8081** and static site with livereload on **localhost:9004**. And to see changes that you just did on your felayout not only on static site but also on TYPO3 site, you need to change felayout path in Theme constants:  
Path to felayout = fileadmin/felayout _projectname/css  
And use command grunt css in your felayout instead of just grunt.

