# Thanks

Firstly thanks for stopping by this guide and considering to contribute to the documentation for the TurtleCoin project. This is an open-source project that continues to move forward from the contributions of others. If documentation is your thing and you are not familiar with git or GitHub, then this is the place to get up to speed and your work will be published in no time.

# Let's get started

You will need a GitHub account, make sure you have one and are logged into the GitHub website.

You'll need git _(command line interface needed, none of the GUIs allows access to all the commands being used, it is a bit tedious typing the commands, however, they become second nature with enough edits.)_ and be able to push and pull from your repo.

    TODO: Explain how to do that ^^ since that requires whole guides, that isn't covered here on this 1st go-around.

Right now that you have access to git and can pull from/push to your repos on GitHub let's continue with how to create/update/re-arrange content for the TurtleCoin wiki.

### Hold up I just want to fix a typo

Well in that case simply navigate to the page and click the edit button. Make your fixes and save, which should create a Pull Request (PR) and you're done. Thanks for paying attention to the details!

### Disclaimer

Nothing in this guide is the "right" way, it is simply a "way" that will work 99% of the time and as someone new to the world of git and GitHub, it is going to cut through an almost vertical learning curve that is git.

As a developer person who is familiar with git and wanting to help with docs, you might find the commands part useful for refreshing on how to interact with the wiki git repo that is in GitHub from the code in the actual repo.

This guides purpose is to break down the barrier that exists to get from "I want to write/contribute docs" to "here is my PR". If anything is not clear or could be made clear, please jump into discord #dev_docs channel and chat about it or even go ahead update the doc.

### Defintions

repo = git repository  
wiki repo = the git repository that powers the wiki tab in a GitHub repo  
PR = pull request  

GitHub's base thing that we interact with on the site is a repo. This gets a bit confusing, however, once you're familiar it no longer causes issues. we can break down the URL and see how it works as well

https://github.com/turtlecoin/turtlecoin-wiki

turtlecoin = the github user or organisation  
turtlecoin-wiki = repo

Furthermore, we care about the code tab and the wiki tab on GitHub. When the guide refers to the repo, it is a reference to the git repo on your computer _(a directory)_ or the code tab on the GitHub website for your repo _(confusing right...)_

# The commands/workflow process

These are the commands and the workflow. Further down in the guide why and explanations and scenarios will be covered. Once understood and you need a reminder of what to do, this is the section you'll be looking for and wanting a quick fix. So it is covered first. Furthermore the commands are in order, deviating from the order will give interesting results. Again this is a how to guide to get from "I want to contribute" to "check out my PR", rather than how to git guide. For the later read [Pro git](https://git-scm.com/book).

Set the stage:
    * when doing work always do work in chunks
        + new guide = a chunk of work
        + update a guide = a chunk of work
        + re-arrange a lot of things = a chunk of work
        + a chunk
            - starts with a new branch *step 6*
            - ends with a PR *step 17*
        + you can work on different chunks at the same time if you do it properly
        +   - step 19 shows this briefly and is explained in detail further down in the scenarios section
    * a chunk of work in git = a branch
    * below the work being done is a new guide: `How-to-contribute-to-the-TurtleCoin-wiki` _(meta!)_
        + the branch for this chunk of work is: `how-to-contribute-to-wiki`


1. fork the repo
  	go to https://github.com/turtlecoin/turtlecoin-wiki
  	click the fork button, wait for it to be done
2. clone the repo locally
  	`git clone https://github.com/your-username/turtlecoin-wiki.git`
3. add wiki repo remote
  	`git remote add wiki-repo https://github.com/your-username/turtlecoin-wiki.wiki.git`
4. add turtlecoin-wiki upstream repo
  	`git remote add upstream https://github.com/turtlecoin/turtlecoin-wiki.git`
	`git remote add upstream-wiki https://github.com/turtlecoin/turtlecoin-wiki.wiki.git`
5. push repo to wiki repo
	`git push wiki HEAD:master`
6. get to work by starting a new branch
	`git checkout -b how-to-contribute-to-wiki`
7. make changes
	create a new file guides/How-to-contribute-to-the-TurtleCoin-wiki.md
	put some content into it
	save it
	`git add guides/How-to-contribute-to-the-TurtleCoin-wiki.md
	git commit`
8. push to wiki repo
	`git push wiki HEAD:master`
9. continue editing on GitHub
    go to https://github.com/your-username/turtlecoin-wiki/wiki/How-to-contribute-to-the-TurtleCoin-wiki
    notice how what you thought would be fine looks messed up
    so edit and keep going, much easier to edit in the browser, grammarly amiright?
10. pull wiki repo back down locally
    `git fetch wiki
    git merge wiki/master`
11. make changes again locally
    edit the file, maybe add an image?
    `git add .` will add all files that have been changed
    `git commit`
12. push changes back to wiki repo to visually inspect everything
	`git push wiki HEAD:master`
	go to https://github.com/your-username/turtlecoin-wiki/wiki/
13. make changes on GitHub
	probably got the image url wrong and it isn't displaying, fix that up and stuff
14. all done, now clean up
	`git fetch wiki
	git merge wiki/master`
15. make sure wiki repo and repo branch are the same
	`git push origin`
16. squash all changes into a single commit
	`git reset $(git merge-base master how-to-contribute-to-wiki)
	git add .
	git commit` this is your chance to make a nice commit message
	`git push origin`  
	now merge your changes to your master branch, so when you do new work you'll have all the changes visible  
	`git checkout master`  
    `git merge how-to-contribute-to-wiki`  
17. create PR  
    this is called pushing changes upstream  
	got to https://github.com/turtlecoin/turtlecoin-wiki/pulls
	click New pull request
	click compare accross forks
	find your repo and branch
	click the button Create pull request
18. done, time to work on the next piece go back to master  
    hang tight here, when you find something else to work on start from step **6** above.  
    celebrate :fireworks:
19. 24hrs later, your PR hasn't been merged into the upstream wiki yet, need to make some updates and you already started work on a new chunk of work, now what?  
    19.1 current working branch is: `how-to-contribute-to-wiki`  
    19.2 last work done was on the wiki repo on GitHub
        need to make sure everything on the wiki repo is saved locally  
        `git fetch wiki`  
        `git merge wiki/master`  
    19.3_alternativley_ last work was done locally in the repo, so save changes  
        `git add .`
        `git commit`  
        `git status`  
        should be all clean
    19.4 now current work is saved, switch back to master and checkout previous branch  
        `git checkout rainborg-she-tips`  
    19.5 can continue from step **7**.
    19.6 then when you get to step **8** do this instead  
        `git push --force wiki HEAD:master`  
    19.7 right keep going through the steps until step **16**, going to do it a bit differently
        `lol - need to figure this out`
    19.8 since the PR already exists your commits will show up automatically so no need for step **17**
    19.9 can go back to your previous branch and continue with that work, part of the above 19.7 was going back to master, so this should work fine  
       `git checkout how-to-contribute-to-wiki`  
    19.10 continue where you were before  
