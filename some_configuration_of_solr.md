# Some configuration of solr

1. Adding solr core  
/mnt/persist/solr  
and then nano solr.xml  
then copy one of the lines and add your own, for example:  
```<core name="nameofwebsite_sv_SE" instanceDir="typo3cores" schema="swedish/schema.xml" dataDir="data/nameofwebsite_sv_SE/" />  
```  
the core name is the name of the site and add the sv_SE or other language code.  
Schema is important for the language and dataDir will have the same name as core name, and it will be created after second step.

2. Check the tomcat status and folder (# is a number):  
ls -lah typo3cores/data/ (there should be no folder with the new site)  
    service tomcat# status  (should say it is running with certain pid)  
    service tomcat# restart   
    service tomcat# status (should say it is now running with other certain pid)  
     ls -lah typo3cores/data/ (the new folder should now be there)
     

### Core Installation



  1. Go to site and check list on root page, click on template -> Default root template. Check what configurations you need. for example:
plugin.tx_solr.solr.port = 8080
plugin.tx_solr.solr.path = /solr/nameofwebsite_sv_SE/
plugin.tx_solr.solr.host = 127.0.0.1

  this will be added in constants. 

  in the tabs go to, Includes -> add Apache Solr - Defaul Configuration (solr) and Pixelant solr search (pax_solr)  

  save and exit.

  Clear general cache. 

  Click on the globe-icon and click on Initialize Solr Connections.

 Go to search, choose the site you made. Click on Index Queue, index maintenance  and index fields, and fix what needs to be done (click on some buttons). 

 Go to Scheduler create new Index Queue worker for your site
 

###  T3KIT installation

Click on themes in the menu to the left  
Choose Expert in the checkbox, and change the search dropdown to "Site related settings"
Find "Features" and change in the "Base solr core name (no spaces): Will be combined with language ISO code in solr path" to the name of the website as the core was named.  
Save  

Click on the lightning symbol and "Initialize Solr connections"

Click on Search in the menu to the left, here you should get an Overview of the Apache Solr servers that has been contacted. 

### Using hosted-solr.com

Solr hosting hosted-solr.com is not supported out of the box. It uses randomly generated string names for the folders containing cores. If you have just a simple single language single domain page, you can override the solr path configuration using typoscript setup (not constants), like this:
```plugin.tx_solr.solr.path = /425cdec5634-myaccount/mycore/```

If you do not have such simple site, you will need to override the path for each language. This requires separate core with additional conditions like in the current setup.