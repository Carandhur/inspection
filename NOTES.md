# Q/A

1.What are the three "areas" in Git, and what does staging actually mean? (Use your own phrasing.)
The working directoy, the stagin area, and the commit area. Staging means a place where validated files rest pendind final shipping and record the final version.

2.What is a branch, really? And what is HEAD?
A branch is a parallel place where you can work, modify and create features isolated from the original stable version of the work. The HEAD is a pointer that tells you in which branch you are standing and working.
A branch isn't a place or a copy of your files - it's a movable pointer to one specific commit. Remember cat .git/HEAD showing ref: refs/heads/update-readme, and the branch being just a 40-character hash in a tiny file? That's the truth. The "parallel work" feeling is the effect of the pointer, not what a branch is. Say it as "a lightweight pointer to a commit" and you've got it airtight.

3.What's the difference between a fast-forward merge and a three-way merge, and what makes Git do one versus the other?
A fast forward merge is when a new branch version of your work is merged with the original or stable version of the work. A three way merge is a merge where git finds that there are more than 2 versions to reconciliate before the commit

4.Why does .gitignore only work on files Git isn't already tracking and why does that mean you should set it up early?
The answer: .gitignore tells Git which untracked files to ignore going forward — but once a file has been committed, Git is already tracking it, and .gitignore has no power to un-track it (you'd need git rm --cached). That's the whole reason early setup matters: ignore .DS_Store before it ever gets committed, and you never have to clean it out. Your answer explained what .gitignore does in general but didn't hit the "already-tracking" mechanism - that's the piece to add.

Git only tracks the added content done through the git add. Thus .gitignore is a file that exclude the content in the root folder that is not meant to be related to the project. It is important to set it before the files we dont want to include get bigger and complicated.

5.Name two things Git will let you do that fail silently (no error, wrong result), and how you'd catch each. (This one's the debugging temperament from today - think about what actually bit you.)
You can modify files in the wrong branch, and you can catch it by verifying the git branch. Two, you can cause a difference between a file name in caps or lower caps, so you better be constant and read every sentence before entering.
