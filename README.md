## Hello World!

This is a test website. Great instructions:  
https://www.atlassian.com/git/tutorials/comparing-workflows

#### Section 1

There is absolutely no information here. None.

#### Section 2

Second git push done with the following steps:  
1) Go to current directory (within repository)  
2) Git status - check if connected (otherwise git clone url)  
3) Git pull origin master - assure all in sync (git status)  
4) Edit README file + save  
5) git status: file needs to be added + committed - DO BOTH  
  - git add README.md  
  - git commit -a -m "Updated Section 2"  

6) git push - u origin master  - this will show any conflicts (origin = when you pulled master, if there is a difference then error): master is the one you push to, -u stands for upstream (remote tracking branch), after this push can be done with 'git push'
7) Check website: mikloshorn.github.io  

First offline: go to new branch - work in that, then upload with git push origin <new-branch e.g. start-website>  

More details on working in branches (without affecting master branch) - e.g. different features, submitted for reviews/feedback (pull requests)  
https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow  
- git checkout -b marys-feature master: -b tells git to create new branch if it does not exist (based on master). On this branch, Mary edits, stages, and commits changes in the usual fashion, building up her feature with as many commits (status + add + commit) as necessary.  
- After working on different branch and reviewing: merge pull request (resolve conflicts if others have worked on repo)  
- Once someone completes a feature, they don’t immediately merge it into master. Instead, they push the feature branch to the central server and file a pull request asking to merge their additions into master  
- You can think of pull requests as a discussion dedicated to a particular branch  
- Once a pull request is accepted, the actual act of publishing a feature is much the same as in the Centralized Workflow. First, you need to make sure your local master is synchronized with the upstream master. Then, you merge the feature branch into master and push the updated master back to the central repository.  
- To make the changes, Mary uses the exact same process as she did to create the first iteration of her feature. She edits, stages, commits, and pushes updates to the central repository. All her activity shows up in the pull request, and Bill can still make comments along the way. If he wanted, Bill could pull marys-feature into his local repository and work on it on his own. Any commits he added would also show up in the pull request. Once all done, the following code uploads (and often merge commits) new feature:  
-- git checkout master  
-- git pull  
-- git pull origin marys-feature  
-- git push  

Possible to rebase the feature onto the tip of master before executing the merge, resulting in a fast-forward merge. (Rebase =  “I want to add my changes to what everyone else has already done.”). Utilizing git rebase during the review and merge stages of a feature branch will create enforce a cohesive Git history of feature merges.  
