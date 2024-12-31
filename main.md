# Git Commands Cheat Sheet

## Git Log
1. **Basic Log**:  
   `git log --oneline`  
   Display commit history in a simplified, single-line format.

2. **Graphical Log**:  
   - `git log --graph`  
     Show a commit graph with a simpler visualization.  
   - `git log --graph --oneline`  
     Combine the graphical view with single-line commits.

3. **Alias: git lg**:  
   - Works similarly to `--graph`.

4. **Statistics**:  
   - `git log --stat`  
     Show statistics about added and deleted lines/files.

5. **Patch Mode**:  
   - `git log -p`  
     Display actual changes in the code (lines added/removed).  
   - `git log -p <commit-id>`  
     Show changes for a specific commit.

6. **Limit Number of Commits**:  
   - `git log -<number> --oneline`  
     Show the last `<number>` commits. Example: `git log -4 --oneline`.

7. **Shortlog**:  
   - `git shortlog`  
     Group commits by author.  
   - `git shortlog -n`  
     Sort grouped commits by the number of commits.  
   - `git shortlog -n -s`  
     List users sorted by the number of commits.  
   - `git shortlog -n -s -e`  
     Include email addresses of users.

8. **Filter by Author**:  
   - `git log --author="user name"`  
     Show commits by a specific user.  
     *Tip*: You can use part of the name and combine with other flags like `-p` or `--oneline`.

9. **Custom Formatting**:  
   - `git log --pretty=format:"%cn %H %h Date:%cd"`  
     Customize commit information:  
       - `%cn`: Committer name  
       - `%H`: Full hash  
       - `%h`: Short hash  
       - `%cd`: Commit date  

10. **Show Merges**:  
    - `git log --merges`  
      Display only merge commits.  
    - `git log --no-merges`  
      Exclude merge commits.

---

## Key Areas in Git
1. **Working Directory**:  
   The files you're actively editing. Changes here are untracked or unstaged.

2. **Staging Area**:  
   Prepares changes for the next commit using `git add`.

3. **Local Repository**:  
   Stores all commits after using `git commit`.

4. **Remote Repository**:  
   Stores commits after pushing using `git push` to a remote server like GitHub.

---

## Git Reset
1. **Basic Reset**:  
   - `git reset <SHA-hash>`  

2. **Mixed Reset**:  
   - `git reset --mixed <SHA-hash>`  
     Discard commit, discard staging changes, keep working directory changes.

3. **Soft Reset**:  
   - `git reset --soft <SHA-hash>`  
     Discard commit, keep staging and working directory changes.

4. **Hard Reset**:  
   - `git reset --hard <SHA-hash>`  
     Discard commit, staging, and working directory changes.

5. **Reset Last N Commits**:  
   - `git reset HEAD~<number>`  

---

## Git Revert
- `git revert <SHA-hash>`  
  Reverse changes of a specific commit by creating a new commit.  
  *Safer than reset because it preserves history.*

---

## Git Commit
1. **Amend Last Commit**:  
   - `git commit --amend`  
     Update the last commit's message or include additional changes.  

2. **Change Author**:  
   - `git commit --amend --author="new author"`  

---

## Git Cherry-Pick
1. **Apply a Commit to Another Branch**:  
   - `git cherry-pick <SHA-hash>`  

2. **Cherry-Pick Without Commit**:  
   - `git cherry-pick --no-commit <SHA-hash>`  

---

## Git Reflog
- `git reflog`  
  Show all local operations (e.g., resets/reverts) to recover changes.

---

## Git Stash
1. **Stash Changes**:  
   - `git stash`  
     Temporarily store changes.

2. **Apply and Remove Stash**:  
   - `git stash pop`  

3. **Apply Without Removing**:  
   - `git stash apply`  

4. **Remove Specific Stash**:  
   - `git stash drop`  

5. **Clear All Stashes**:  
   - `git stash clear`  

6. **View Stashes**:  
   - `git stash list`  

7. **Inspect Specific Stash**:  
   - `git stash show -p stash@{<index>}`  

---

## Rebasing with Squashing in Local Repository
1. Create a new branch:  
   - `git checkout -b <feature-branch>`  

2. Make changes and commit multiple times.

3. View log:  
   - `git log`  

4. Rebase interactively:  
   - `git rebase -i <SHA-hash>`  

5. Replace messages with "s" (squash) except the first one.

6. Merge the feature branch into the main branch.
