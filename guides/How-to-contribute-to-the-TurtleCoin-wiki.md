# Thanks

Firstly thanks for stopping by this guide and considering to contribute to the documentation for the TurtleCoin project. This is an open-source project that continues to move forward through the contributions of others. If documentation is your thing and you are not familiar with git or GitHub, then this is the place to get up to speed and your work will be published in no time.

# Let's get started

You ideally need to install git _(command line interface needed, none of the GUIs I've used allows access to all the commands being used)_ and be able to push and pull from your repo.

    TODO: Explain how to do that ^^ since that requires whole guides, that isn't be covered here.

Right now that you have access to git and can pull and push to your repos on GitHub let's continue with how to create/update/re-arrange content for the TurtleCoin wiki.

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

These are the commands and the workflow. Further down in the guide why and explanations and scenarios will be covered. Once understood and you need a reminder of what to do, this is the section you'll be looking for and wanting a quick fix. So it is covered first. Plus 

1. fork the repo
2. clone the repo locally
3. add wiki repo remote
4. push repo to wiki repo
5. setup a new branch
6. make changes
7. push to wiki repo
8. continue editing on GitHub
9. pull wiki repo back down locally
10. make changes again locally
11. push changes back to wiki repo to visually inspect everything
12. make changes on GitHub
13. all done, now clean up
14. make sure wiki repo and repo are the same
15. sqaush all changes into a single commit
16. create PR
17. done