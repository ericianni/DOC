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

#### History

_Git_ is an open source VCS created in 2005 by Linus Torvalds, who also developed Linux. He created it to better manage the distributed development of the Linux kernel. Since then, it has grown to be one of the most popular VCS's available and led directly to the creation of the industry standard _GitHub_.

#### Git Basics
In it's most basic form, _Git_ is a command line program that allows users to designate any folder on their computer as a local _Git_ repository by using `git init`. This repo can then be stored centrally almost anywhere, but for this class we will be using the aforementioned _GitHub_. Users can also _clone_ remote repos and create an exact copy locally.

As users make changes to the directory _Git_ is maintaining a list of these changes. Users can view all the changes by using `git status`. This will categorize all changes as either _not staged_ or _untracked_. Any files that have been added to the repo already are labled _not staged_ when modified. Any files that haven't been added to repo, but have been changed/created, are labled _untracked_. 

**[There will be an image here showing how they look on the commandline]**

Users can use `git add <filename>` to _stage_ any file, both _unstaged_ and _untracked_. These files will then be added to the repo when the user runs `git commit`. Now these files will show up as _not staged_ instead of _untracked_.

**[There will be an image here showing how commits look]**

_Commits_ not only add files to the repo, but it they act as signposts and are assigned a unique identifier. These identifiers can be used to revert back to the codebase at this exact moment in time. Each _commit_ is also labled with the username of the author.

**[There will be a short video here demonstrating these commands with a practicle example]**


#### Intermediate Git

Now let's look at some more advanced features of _Git_. One of the beautiful things that _Git_ provides is the abililty to create _branches_. Simply put, a _branch_ is an offshot of the current state of the codebase where a user can make changes and not effect the other states/_branches_ of the repo.

These _branches_ are useful when implenting new features. A developer can _checkout_ a branch and start changing the files without risking breaking the stable version that existed before. This system also makes it easy for other team members to continue working on other features without having to worry about what eachother are doing. 

To create a _branch_ a user simply uses the `git branch <branch_name>` command and `git checkout <branch_name>`. It is possible to switch between _branches_ at will and _Git_ will restore the correct repo state.

**[There will be an image here showing creating and switching branches]**

Once the feature _branch_ is stable, the user can then _merge_ it back into any other _branch_ (often _master_). This is done by going to the _branch_ you want to merge _into_ and running `git merge <branch_to_be_merged>`. If no _merge conflicts_ exist _Git_ will automatically handle updating all the files as needed. 

**[There will be an image here showing merging a branch with no merge conflicts]**

A _merge conflict_ occurs when changes have been made in the same place in _both_ branches that are being merged. At this point _Git_ will stop the merge and require the user to manually select which branch's changes, or combination of the two, are kept. Once all _conflicts_ have been resolved _Git_ will then allow for the _merge_ to be completed.

**[There will be a series of images showing a merge conflicts and how to resolve it]**

**[There will be a short video demonstrating branching]**

Up until this point we have been using _Git_ as a purely local solution to version control. This does not allow for the collaborative benefits of a VCS. In order for allow others work on the same codebase, we need need to _push_ these changes to a central repo that the entire team can access.

How this is accomplished is different depending on where you are storing the central repo, but for this class we will be using _GitHub_. The first step is to create a _remote_.

As you will see in the assignment, each _GitHub_ repo has a unique URL. We will use this to create our _remote_ that we will _push_ our changes.

This is done using `git remote add <remote_name> <remote_url>`. 

**[There will be an image here showing how to create a remote]**

Now the user can use `git push <remote_name> <branch_name>` to push a given local branch to the central repository. Please note that this will only work if no one else has pushed changes since you last _pulled_ changes from the central repository. If this has happened _Git_ will reject your _push_ and instructor you to _pull_ and merge your changes into the current state of the central repo.

Users will have to use 'git pull` command which _fetches_ any changes and attempts to _merge_ them into your current branch. Any _merge conflicts_ will have to be dealt with as described above. Once everything is _merged_ the user can then _push_ the branch to the central repo.

**[There will be a short video demonstrating pushing and pulling]**

### Conclusion

Hopefully you have gathered some useful information about how VCS's work in the abstract and then in practice using _Git_. You will go onto get hands-on experience with this week's activity: _Git Intro_ (link to the Canvas assignment). When it comes time for the team project you will be using _Git_ and _GitHub_ quite a bit so make sure you are practicing and doing additional reading if you need further clarification.

### Resources

* [Pro Git Ebook](https://git-scm.com/book/en/v2)
  * [Chapter 2: Git Basics](https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository)
  * [Chapter 3: Git Branching](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell)
  * [Chapter 5: Distributed Git](https://git-scm.com/book/en/v2/Distributed-Git-Distributed-Workflows)
  * [Chapter 6: GitHub](https://git-scm.com/book/en/v2/GitHub-Account-Setup-and-Configuration)
