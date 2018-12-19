## Setup
|command|description|example|
|-------|-----------|-------|
|git config --global user.name \<username\>|Specify the username of your profile|git config --global user.name "test-user"|
|git config --global user.email \<email\>|Specify the email of your profile|git config --global user.email "test-user@test.com"|
|git init|Create a local repo|git init|
|git clone \<path\>|Create a local copy of the target repo|git clone http://test.com/test.git|
|git remote -v|List remote connections|git remote -v|
|git remote \<name\> \<path\>|Connect local repo to a remote repo|git remote add origin http://test.com/test.git|
|git remote rm \<name\>|Remove the connection to the remote repo|git remote rm origin|
|git remote rename \<old-name\> \<new-name\>|Rename a remote connection|git remote rename origin-old origin-new|

## Basic Operations
|command|description|example|
|-------|-----------|-------|
|git status|Show all changes|git status|
|git add \<file\>|Add changes in a file to staging|git add test-file|
|git add \*|Add all changes to staging|git add \*|
|git commit -m \<message\>|Commit staged changes|git commit -m "test message"|

## Display
|command|description|example|
|-------|-----------|-------|
|git show \<object\>|Show various types of objects|git show commit-id|
|git diff \<file\>|Show the changes made to a file|git diff test-file|

## Branch
|command|description|example|
|-------|-----------|-------|
|git branch|List local branches|git branch|
|git branch -a|List both local and remote branches|git branch -a|
|git branch -d \<branch\>|Delete a local branch|git branch -d test-branch|
|git checkout \<branch\>|Switch to a branch|git checkout test-branch|
|git checkout -b \<new-branch\> \<base-branch\>|Create a new branch off the base branch|git checkout -b test-branch master|

## Syncing
|command|description|example|
|-------|-----------|-------|
|git fetch \<remote\> \<branch\>|Download from a branch|git fetch origin master|
|git pull \<remote\>|git fetch + git merge|git pull origin|
|git push \<remote\> \<branch-name\>|Push code to remote server. Create one if none exist|git push origin master|
|git push -u \<remote\> \<branch-name\>|Add upstream (tracking) reference to local branch. You can use git pull without any arguments after this|git push -u origin master|
|git merge \<branch\>|Merge a branch into the working branch|git merge master|
|git rebase \<upstream\> \<branch\>|Change the base of your branch to the head of upstream|git rebase master test-branch|

## Undo
|command|description|example|
|-------|-----------|-------|
|git checkout -- \<file\>|Discard changes in a file from the working directory|git checkout -- test-file|
|git clean -i \<path\>|Remove local untracked files|git clean -i test-path|
|git reset HEAD \<file\>|Unstage changes in a file|git reset HEAD test-file|
|git reset HEAD --hard \<file\>|Discard changes in a file from both the staged snapshot and working directory|git reset HEAD --hard test-file|
|git reset HEAD~1|Remove the latest commit from the current branch|git reset HEAD~1|
|git revert \<commit\>|Create a new commit which inverses the specified commit|git revert HEAD~3|
|git cherry-pick \<commit\>|Apply the changes introduced by the specified commit|git cherry-pick HEAD~3|

## Log
|command|description|example|
|-------|-----------|-------|
|git log \<remote\> \<branch\>|Show the history of commits|git log origin master|
|git log \<remote\> \<branch\> --all --decorate --oneline --graph|Include a readable graph|git log origin master --all --decorate --oneline --graph|

## Stash
|command|description|example|
|-------|-----------|-------|
|git stash list|List all stashes|git stash list|
|git stash show \<stash\>|Show changes in the stash|git stash show test-stash|
|git stash save \<stash\>|Save changes to a stash and roll back to HEAD|git stash save test-stash|
|git stash apply \<stash\>|Apply a stash and keep the stash|git stash apply test-stash|
|git stash pop \<stash\>|Apply a stash and drop the stash|git stash pop test-stash|
|git stash drop \<stash\>|Remove a stash|git stash drop test-stash|

## Other
|command|description|example|
|-------|-----------|-------|
|git --version|Check the version of your git|git --version|

## Symbol
|command|description|example|
|-------|-----------|-------|
|\~\[\~\]|Move up len(\~) levels in the hierarchy, via the first parent if a commit has more than one parent|git reset HEAD\~\~|
|\~\[n\]|Move up n levels in the hierarchy, via the first parent if a commit has more than one parent|git reset HEAD\~2|
|\^\[\^\]|Move up len(\^) levels in the hierarchy, via the first parent if a commit has more than one parent|git reset HEAD\^\^|
|\^\[n\]|Move up to the n\'th parent when a commit has more than one parent|git reset HEAD\^2|
