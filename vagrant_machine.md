# Vagrant machine

How to set up a vagrant machine for your site

1. Clone the master branch of [vagrant-machine](https://bitbucket.org/pixelant/vagrant-machines) repository to your local machine
2. Inside of the cloned repository, find the "configuration.yml" file.
 ```
      .
      ├──shared
      |   ├── configuration
      |         ├── configuration.yml```

3. Open it in a texteditor and make the necessary changes:


```
---
MACHINE_NAME: 'NameOfTheMachine' <--Change to the name of the project
IP: '192.168.15.XX' <-- Change to an IP that is not used
HOSTNAME: 'NameOfTheSite.se.vagranthost' <-- Change the hostname
ALIASES: 'NameOfTheSite.en.vagranthost' <--Change the hostname
# uid:domainname uid:domainname ...
SYS_DOMAINS: '1:NameOfTheSite.se.vagranthost' <--Change 
# uids comma separated
SYS_TEMPLATE_EMPTY_BASEURL: '1'
# corename:language corename:language ...
SOLR_CORES: 'NameOfTheSite_se:swedish' <--Change to the correct name of the solr core found on server
DBNAME: 'NameOfTheDB' <-- Change to the real name of DB, can be found in localconfiguration.php file on server.
DBUSER: 'NameOfTheDBUser' <-- Change to the real user of DB, can be found in localconfiguration.php file on server.
DBPWD: 'PasswordOfTheDB' <-- Change to the real password of DB, can be found in localconfiguration.php file on server.
DBDUMPFILE: '/mnt/persist/mysqldump/NameOfTheSite.sql.bak' <-- Change to the real name of DB, can be found in localconfiguration.php file on server.
REMOTEINSTALLATION: '/mnt/persist/www/sites_docroot/NameOfTheSite' <-- Change to the name of the site
REMOTEHOST: 'NameOfTheSiteUrl' <-- Change to the url you want to fetch all the data from
REMOTEPORT: 22
MAIN_REPO: 'git@bitbucket.org:pixelant/NameOfTheSite.git' <-- Change to the correct repository of the site 
MAIN_REPO_BRANCH: 'NameOfTheBranch' <-- Change to the correct branch, master, develop or other
# gitRepository,felayoutName,branch gitRepository,felayoutName,branch ...
FELAYOUT_REPOS: 'git@bitbucket.org:pixelant/NameOfTheSitesFeLayout.git,NameOfTheSitesFeLayout,big' <-- Change to the correct felayout repository
SYNC_FOLDERS: 'fileadmin/user_upload/ uploads/ typo3conf/l10n/ fileadmin/example_files/' ```

4 . Save your changes.


---

Create a branch for the vagrant machine

1. In your terminal, create a new branch with you new project
2. git checkout -b NameOfTheNewBranch
3. Commit your changes and push to your new branch
4. git push -u origin NameOfTheNewBranch 