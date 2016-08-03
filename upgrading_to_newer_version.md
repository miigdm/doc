# Upgrading to newer version

It is  easy to upgrade it to latest version. We are assuming you have a t3kit project where you didn't do changes in the PHP code. E.g. didn't install extra extensions. Here are steps to follow: 
 1. Make sure to commit all the code changes you have to the repository. 
 2. If you used separate repository (which you should), you should add upstream remote: ```git remote add upstream git@github.com:t3kit/t3kit.git```
 3. Now fetch all the newest version of t3kit from upstream: ```git fetch upstream```
 4. Next step should be merge these versions into your version. You can get conflicts in this step most often, if you have a lot of commits, so keep this in mind: ```git merge upstream/master```
 5. Update sub-modules to their respective version: ```git submodule update```
 6. Last step is to check Install tool for database changes. It is a good idea to check t3kit news/newsletter for breaking changes between versions you upgraded and fix those.

