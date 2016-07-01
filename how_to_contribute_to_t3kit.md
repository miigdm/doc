# How to contribute to t3kit


#### Short description about how to add more code to our t3kit (and TYPO3 community extensions in general).

t3kit consist of 9 repositories all publicly hosted on github:
https://github.com/t3kit

First step is creating github account (or login to an existing one) and finding the correct repository. I have added nice descriptive labels for them, in 99% you will be contributing to these 3 repositories:
- t3kit - contains all extensions as submodules and TYPO3
- theme_t3kit - the HTML templates and less files for the site
- felayout_t3kit - frontend process with starting HTML, CSS and javascript files

The rest of the t3kit code base is in community repositories in github or our repositories in bitbucket. You can always find them easily by checking .gitmodule file in the main t3kit repository. If the bug is in any of the community or bitbucket extensions, please submit the fix there first and link it to us. If you are unsure where the fix belongs, consult me or Mats on it (since frontend fixes go to the theme or felayout).

How to submit fix properly: on both github and bitbucket there is a process of submittion pull requests, described best here:
https://yangsu.github.io/pull-request-tutorial/
https://www.atlassian.com/git/tutorials/making-a-pull-request/how-it-works

It is preferred that you use your own repository forks to push pull requests, so we do not have to cleanup the branches afterwards.

What do I need to think about when contributing? Does my code:

- work with multi-site/multi-language
- work with the current theme of t3kit
- use theme variables
- comes with default configuration, which does not change old websites
- not modify any existing default behaviour for backend users
- ship with correct access rights for backend user groups defined in t3kit (might need update of t3kit_db)
- not contain any customer specific comments or pictures
- work on the current version of PHP used on our servers
- have sufficient comments in the commits with proper tags to indicate for other developers what to do after upgrade (**more here**: https://github.com/t3kit/t3kit#contributing )

If you have any questions regarding how to contribute or something is not clear, feel free to ask Jozef.

 