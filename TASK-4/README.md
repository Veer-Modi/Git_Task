# Git And GitHub

## **Task List: Focused on Advanced Git Operations**

## **Part 1: Understanding and Using `git stash`**

### **Task 1: Save Changes Temporarily with `git stash`**

#### 1. Make changes to a file without committing:  

```bash
echo "Temporary changes" >> temp-file.txt
```

- It edit __`temp-file.txt`__ with adding message __`temporary changes`__.

#### 2. View the status of changes:  

```bash
git status
```

- It shows untracked files, modified files, stage of commit.

- **Output**:  
```
Changes not staged for commit:
modified:   temp-file.txt
```

#### 3. Stash the changes:  

```bash
git stash
```

- It saves uncommitted changes,which means It allows you to switch branches or work on something else.

- This command saves changes to a stash and restores the working directory to the last commit state.

#### 4. View the stashed changes:  

```bash
git stash list
```

- It shows all the stashed changes which are saved in repository.
-  Each stash is shown with a name, such as __`stash@{0}`__, __`stash@{1}`__, and so on, along with the commit reference and a brief description.

- **Output**:  
```
stash@{0}: WIP on main: 27e5f23 Added temporary changes
```

### **Task 2: Apply and Drop Stashed Changes**

#### 1. Apply the most recent stash:  

```bash
git stash apply
```

- It's restores the recent stashed changes to your working directory without removing them from the stash list.

#### 2. Drop the most recent stash after applying it:  

```bash
git stash drop
```

- The command __`git stash drop`__ is used to remove a specific stash from the stash list. It doesn't apply the changes it simply deletes the stash you specify.

#### 3. Alternatively, to apply a specific stash:  
```bash
git stash apply stash@{1}
```

- The command __`git stash apply stash@{1}`__ is used to apply the changes from the stash with the identifier __`stash@{1}`__ to your working directory.

### **Task 3: Stash Untracked Files**

#### 1. Stash changes, including untracked files:  
```bash
git stash -u
```

- This command stashes both tracked and untracked files,allowing to save all the work in progress while keeping working directory clean.
- __`-u`:__
  - It includes untracked files in the stash.

#### 2. Apply stashed changes including untracked files:  
```bash
git stash apply
```

- It's restores the recent stashed changes to your working directory without removing them from the stash list.

---

## **Part 2: Rewriting History with `git rebase`**

### **Task 4: Rebase Commits to a New Base**

#### 1. Rebase the current branch onto `main`:  
```bash
git rebase main
```

- Moves all commits from your current branch to start on top of the latest commit in the __`main`__ branch.
- Rewrites the commit history to make it look as though your branch was created from the current state of __`main`__.
- This command applies the commits from your current branch on top of the latest commit from `main`.

#### 2. Resolve any conflicts that may arise during rebase, and continue:  
```bash
git rebase --continue
```

- Resumes the rebase process after you have resolved conflicts.
- Applies the remaining commits on top of __`main`__.

### **Task 5: Canceling a Rebase**

#### 1. If a rebase goes wrong, abort it:  
```bash
git rebase --abort
```

- Restores the branch to its original state before the rebase started.

---

## **Part 3: Interactive Rebase (`git rebase -i`)**

### **Task 6: Use Interactive Rebase to Modify Commit History**

#### 1. View the last few commits:  
```bash
git log --oneline
```

- Displays a concise, one-line summary of the most recent commits.
- __`Ouput`:__
```bash
d3e2f1c Fix a typo in README.md
c4b5a7b Add login page
a2d9e3f Initial commit
```

#### 2. Start an interactive rebase for the last 3 commits:  
```bash
git rebase -i HEAD~3
```

- Initiates an interactive rebase for the last 3 commits.
- Opens your default text editor (e.g., __`vim`__, VS Code, nano) with a list of commits.
- This opens an editor with the list of commits in the last 3 commits.
- __Editor View:__
```bash
pick d3e2f1c Fix a typo in README.md
pick c4b5a7b Add login page
pick a2d9e3f Initial commit
```

#### 3. Modify the commits by changing `pick` to one of the following:
- __`squash` (combine commits):__
  - Combines the commit with the one before it.
  - __Example:__
```bash
pick d3e2f1c Fix a typo in README.md
squash c4b5a7b Add login page
pick a2d9e3f Initial commit
```

- __`reword` (edit commit message):__
  - Allows you to edit the commit message.
  - __Example:__
```bash
pick d3e2f1c Fix a typo in README.md
reword c4b5a7b Add login page
pick a2d9e3f Initial commit
```

- __`edit` (edit commit content):__
  - Pauses the rebase to allow you to make changes to the commit's content.
  - __After making changes, continue the rebase:__
``` bash
git rebase --continue
```

- __`drop` (remove commit):__
  - Removes the commit entirely.
  - __Example:__
```bash
pick d3e2f1c Fix a typo in README.md
drop c4b5a7b Add login page
pick a2d9e3f Initial commit
```

#### 4. Example of squashing two commits:
- Change the second commit from `pick` to `squash` and save.
```bash
pick d3e2f1c Fix a typo in README.md
squash c4b5a7b Add login page
pick a2d9e3f Initial commit
```

- Git will combine the commit messages for the squashed commit.
```bash
# This is a combination of 2 commits.
# The first commit's message:
Fix a typo in README.md

# The second commit's message:
Add login page
```

### **Task 7: Complete Interactive Rebase**

#### 1. After modifying the commits, save and close the editor.
#### 2. Resolve any conflicts if prompted, then continue the rebase:  
```bash
git rebase --continue
```

---

## **Part 4: Cherry-Picking Commits (`git cherry-pick`)**

### **Task 8: Pick a Specific Commit**

#### 1. View the commit history to find the commit hash you want to cherry-pick:  
```bash
git log --oneline
```

#### 2. Cherry-pick a specific commit by its hash:  
```bash
git cherry-pick <commit-hash>
```
- **Example**:  
```bash
git cherry-pick e23d8a7
```

#### 3. Resolve conflicts if any, then commit the changes:  
```bash
git add .
git cherry-pick --continue
```

---

## **Part 5: Tagging Commits (`git tag`)**

### **Task 9: Tag a Commit**

#### 1. Tag the current commit with a version number:  
```bash
git tag -a v1.0 -m "Initial release"
```

#### 2. List all tags:  
```bash
git tag
```

### **Task 10: Tag a Specific Commit**

#### 1. Tag a specific commit by its hash:  

```bash
git tag -a v1.1 <commit-hash> -m "Bug fix"
```

### **Task 11: Push Tags to Remote**

#### 1. Push a specific tag to the remote repository:  
```bash
git push origin v1.0
```

#### 2. Push all tags to the remote repository:  
```bash
git push --tags
```

---

## **Part 6: Working with Remote Repositories**

### **Task 12: Add a Remote Repository**

#### 1. Add a remote repository URL to the project:  

```bash
git remote add origin https://github.com/username/repo.git
```

### **Task 13: Fetch Changes from Remote**

#### 1. Fetch changes from the remote repository without merging them:  
```bash
git fetch origin
```

#### 2. View fetched branches:  
```bash
git branch -r
```

### **Task 14: Pull Changes from Remote**

#### 1. Pull the latest changes from the remote repository and merge them into the local branch:  
```bash
git pull origin main
```

### **Task 15: Push Changes to Remote**

#### 1. Push local changes to the remote repository:  
```bash
git push origin main
```

#### 2. Push a new branch to the remote repository:  

```bash
git push origin feature-branch
```

### **Task 16: Delete Remote Branch**

#### 1. Delete a remote branch:  

```bash
git push origin --delete feature-branch
```

---

## **Part 7: Forking and Contributing to Open-Source Projects**

### **Task 17: Fork a Repository on GitHub**

#### 1. Go to a repository on GitHub and click **Fork** in the top right corner to create your own copy of the repository.

#### 2. Clone the forked repository to your local machine:  
```bash
git clone https://github.com/your-username/repo.git
```

### **Task 18: Make Changes and Commit**

#### 1. Create a new branch for your changes:  
```bash
git checkout -b fix-typo
```

#### 2. Make changes to the code (e.g., fix a typo in `README.md`), stage, and commit them:  
```bash
git add README.md
git commit -m "Fixed typo in README.md"
```

### **Task 19: Push Changes to Your Fork**

#### 1. Push the changes to your remote fork:  
```bash
git push origin fix-typo
```

### **Task 20: Create a Pull Request**

#### 1. Go to your forked repository on GitHub, click on **Compare & Pull Request**.
#### 2. Write a description of your changes and submit the pull request to the original repository.

### **Task 21: Sync Your Fork with the Original Repository**
#### 1. Add the original repository as a remote source:  
```bash
git remote add upstream https://github.com/original-owner/repo.git
```

- Addes the original repository as a remote repository.

#### 2. Fetch changes from the original repository:  

```bash
git fetch upstream
```

- Fetch the changes from original repository.

#### 3. Merge changes from the original repository into your local branch:  

```bash
git checkout main
git merge upstream/main
```

- First switches to __`main`__ branch then merge local branch.

#### 4. Push the changes to your fork:  

```bash
git push origin main
```

- It push __`main`__ branch.

---
