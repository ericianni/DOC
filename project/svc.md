### What is a Version Control System (VCS)?
For much of your course of study here at OSU, you have probably had a very straightforward workflow when completing your assignments. It probably looked something like this:

* Create files on your local computer
* Edit files and save changes
* Test out changes you just made
* Repeat until project is done

This works very well for the fairly simple projects you have worked on in your other classes and is well suited for single programmer developer endeavours. This is not so true as the complexity of the systems being created increases and you add more programmers to the mix.

Now this simple workflow doesn't work anymore as there are new considerations that must be addressed.

* Multiple programmers need to work on the same codebase at the same time
* Changes made by multiple programmers need to be combined so other team members can access the new code
* There needs to be a way to undo changes that introduce bugs into the codebase

Version Control Systems (VCS) help with the above problems by creating a centralized repository (repo) for the project files. This means that developers do not have to ask the other team members to send them their changes as they are all checked in to this central repo.

VCS's also allow for the _merging_ of changes into the centralized codebase. _Merges_ require any _conflicts_ in the code to be addressed and fixed before the changes can be incorporated into the repo. This means that if multiple members change the same lines of code it needs to be manually addressed to ensure which changes should be kept.

Most VCS's create historical records of changes made to the codebase. This means that changes usually are tagged by the author and they are timestamped. This allows for teams to see who made what changes and when in case something needs to be updated or fixed. It also allows for these changes to be _rolled back_ and the codebase reverted to a previous state. This is very useful when a bug is introduced that isn't easily fixed and the team wants to have a stable version to work with or deploy.


### Typical Features of VCS

Every VCS will contain some form of the following actions.

* __Add__  
  Developers need a way to add files to the repo
* __Commit__  
  Developers need a way to push changes to existing files to the repo
* __Update__  
  Developers need a way of getting the most up-to-date versions of files in the repo

### Centralized vs Decentralized VCS

There are two main types of VCS solutions: centralized vs decentralized.

**[There will be an image here showing the difference]**

* __Centralized__ systems store all the files in a central repo. As developers make changes, they are immediately sent to the centralized repo and made available to the whole team.
* __Decentralized__ systems also have a central repo with all the files, but changes made by individual developers are not immediately sent to the main repo. Each developer has a mini VCS on his or her local machine where changes can be committed _without_ being made available to the team. This allows for developers to work on features individually and only push the changes to the central repo when ready.

For this class you will be using a __decentralized__ VCS called _Git_.

### Brief Git Overview

_Git_ is an open source VCS created in 2005 by Linus Torvalds, who also developed Linux. He created it to better manage the distributed development of the Linux kernel. Since then, it has grown to be one of the most popular VCS's available and led directly to the creation of the industry standard _GitHub_.




