## Essential Git Commands

**Adding and Committing Files Together**
git commit -am "commitMessage"
<br>
**Creating and Switching to a Git Branch**
git checkout -b branchName
<br>
**Delete a Git Branch**
git branch -d branchName (Safe deletion)
git branch -D branchName (Forceful deletion)
<br>
**Renaming a Git Branch**
git branch -m oldBranch newBranch
git branch -m newBranchName
<br>
**Unstaging a Specific File**
git reset filename
<br>
**Discarding Changes to a Specific File**
git checkout -- filename
<br>
**Updating Your Last Git Commit**
git commit --amend -m 'message'
<br>
**Stashing Changes**
git stash
<br>
**Restore Latest Stashed Changes**
git stash apply
git stash pop
<br>
**Reverting Git Commits**
git revert commitHash
<br>
**Resetting Git Commits**
git reset --soft HEAD^
git reset --mixed HEAD^
git reset --hard HEAD^
<br>
