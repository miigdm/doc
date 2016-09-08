# Static site

We have possibility to use static web server for every our project. It means we can quickly deploy site and discuss some questions with designers, others developers, PM etc. 
Use command ```grunt pushSite``` to automatically deploy site.

* If the project is hosted on bitbucket, the static site will be located on our test server:
http://felayout_projectName.testserver.pixelant.nu/
* If the project is hosted on github, the static site will be located:
https://pixelant.github.io/felayout_projectName/

Before using command ```grunt pushSite``` we should commit all changes on master branch of local Git repo. It is also possible to make static sites from other branches.
