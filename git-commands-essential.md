# Essential Git Commands

**1. Adding and Committing Files Together**<br>
git commit -am "commitMessage"<br>
<br>
**2. Creating and Switching to a Git Branch**<br>
git checkout -b branchName<br>
<br>
**3. Delete a Git Branch**<br>
git branch -d branchName (Safe deletion)<br>
git branch -D branchName (Forceful deletion)<br>
<br>
**4. Renaming a Git Branch**<br>
git branch -m oldBranch newBranch<br>
git branch -m newBranchName<br>
<br>
**5. Unstaging a Specific File**<br>
git reset filename<br>
<br>
**6. Discarding Changes to a Specific File**<br>
git checkout -- filename<br>
<br>
**7. Updating Your Last Git Commit**<br>
git commit --amend -m 'message'<br>
<br>
**8. Stashing Changes**<br>
git stash<br>
<br>
**9. Restore Latest Stashed Changes**<br>
git stash apply<br>
git stash pop<br>
<br>
**10. Reverting Git Commits**<br>
git revert commitHash<br>
<br>
**11. Resetting Git Commits**<br>
git reset --soft HEAD^<br>
git reset --mixed HEAD^<br>
git reset --hard HEAD^<br>
<br>
