# Git And GitHub

---

## Part 1: Git Basics

### Task-1: Install And Configure Git

#### 1. Install Git form git-scm.com.

- For Git Bash Terminal install Git Bash from this link.

#### 2. Configure your global Git settings:

```bash
git config --global user.name "Your Name"
git conig --global user.email "your-email@example.com"
```

- **`git config`:** It is a git command which is use to view **configuration option** for git.
- **`--global`:** In which user details will set to all repository in the user Account.
- Its configure name and email address which is use to link with github account globally.

#### 3. Verify the configuration:

```bash
git config --list
```

- **`--list`:** It is used to check/verify the user cofiguration details.

### Task-2: Initailize a Repository

#### 1. Create a directory and initailize it as a Git repository:

```bash
mkdir MyProject
cd MyProject
git init
```

- **`mkdir MyProject`:** It stands for **make directory** with named **`MyProject`**.
- **`cd MyProject`:** IT stands for **Change Directory** and it change the path and open the file **`MyProject`**.
- **`git init`:** Its **initailize new empty repository** in the local of the computer.
  - Also make hidden file with git objects which is used to tack changes in the file before commit.

  ---

## Part 2: Basic Workflow

### Task-3: Creating and Commiting Files

#### 1. Create a file:

```bash
echo "Hello Git" > file1.txt
```

- Create a **new file** and **adds a message** which is written in the **`"Hello Git"`**

### 2. Stage and commit the file:

```bash
git add file1.txt
git commit -m "Inital commit: Added file1.txt"
```

- **`git add file1.txt`:** It add the **`file1.txt`** to staging area to commit the changes.
- **`git commit -m "Initail commit: Added file1.txt"`:** It save the change with a message **`-m`** written **`"Inital commit: Added file1.tx"`**.

### Task-4: Viewing Changes

#### 1. Modify the file:

```bash
echo "Git is awesome!" >> file1.txt
```

- **`>>`:** Redirect the text into the file with any changes in the file.

#### 2. Check thestatus and differences:

```bash
git status
git diff
```

- **`git status`:** It show the status of a working directory like untracked files, modified files, and files in staging area which is ready to commit.
- **`git diff`:** It show the difference between previous commit and current changes in the directory .

### Task-5: Undoing Changes

#### 1. UNstage a staged file:

```bash
git reset file1.txt
```

- This command removes **`file1.txt`** from the staging area.

#### 2. Discoard uncommitted changes:

```bash
git checkout -- file1.txt
```

- It replaces the content of **`file1.txt`** in your working directory with the version of the file from the last commit (HEAD).
- Any changes made to **`file1.txt`** that are not staged will be permanently lost.
- If the file is staged but not committed, the changes in the staging area will remain intact.

---

## Part 3: Branching and Merging

### Task-6: Branch Management

#### 1. Create a Branch and switch to it:

```bash
git checkout -b feature-branch
```

- **`git checkout`:** It switches to new branch.
- **`-b`:** It create new branch with named **`feature-branch`**.

#### 2. List branches:

```bash
git branch
```

- It gives all branches List.

#### 3. Rename a branch:

```bash
git branch -m feature-branch feature-enchanced
```

- **`-m`:** It is used to rename the old branch to new branch.

### Task-7: Merging branches

#### 1. Merge `feature-enchanced`into `main`:

```bash
git checkout main
gt merge feature-enchanced
```

- First switch to **`main`** branch.
- Then merge the file and it combines all change into **`main`** branch.

### Task-8: Handling Merge Conflicts

#### 1. Crete two conflicting branches and resolve a conflict manually:

```bash
git merge <branch-name>
```

- Create two branch (branch-A & branch-B).
- Use git checkout to change branch to main then merge both branch to main.
- A merge conflict will occur.
- Resolved the merge conflict by editing the file manually.

#### 2. Use:

```bash
git add <resolved-file>
git commit
```

- Now, add the resolved file to the staging area for the commit the changes.
- Commit the resloved file to save the changes.

---

## Part 4: Remote Repository

### Task-9: Remote Setup

#### 1. Add a Remote repository:

```bash
git remote add origin https://github.com/your-useraname/repo.git
```

- **`git remote add`:** This command adds a remote repository to your local Git project.
- **`origin`:** This is a default name for the remote repository.
- **`https://github.com/your-useraname/repo.git`:** This is URL of your remote repository.

#### 2. Verify the remote:

```bash
git remote -v
```

- This command displays the list of remote repositories connected to your local repository along with their URLs.

### Task-10: Push and Pull

#### 1.Push changes to the remote repository:

```bash
git push -u origin main
```

- **`git push`:** Sends (uploads) your committed changes from the local repository to the remote repository.
- **`-u`:** Sets up the upstream branch. This means the local branch (**`main`**) is linked to the remote branch (**`origin/main`**) so future pushes or pulls can be done simply with **`git push`** or **`git pull`** (without specifying the branch).
- **`origin`:** Refers to the remote repository name (default is **`origin`**).
- **`main`:** Specifies the branch being pushed.

### Task-11: Cloning a Repository

#### 1. Clone a remote repository:

```bash
git clone https://github.com/your-username/repo.git
```

- **`git clone`:** A Git command to copy a remote repository to your local machine.
- **`https://github.com/your-username/repo.git`:** The URL of the remote repository you want to clone.

---

## Part 5: Advanced Git

### Task-12: Stashing Changes

#### 1. Save uncommitted changes:

```bash
git stash
```

- Saves your uncommitted changes (both staged and unstaged) and clears your working directory.
- Allows you to work on a clean state without losing your progress.

#### 2. Apply stached changes:

```bash
git stash apply
```

- Reapplies the most recent stashed changes to your working directory.
- Does not remove the stash entry (it remains saved until explicitly dropped).

#### 3. Drop the stach:

```bash
git stash drop
```

- Deletes a specific stash entry (or the most recent one by default).
- Use this after you no longer need the stashed changes.

### Task-13: Tagging Commits

#### 1. Create and annotate a tag:

```bash
git tag -a v1.0 "Version 1.0 release"
```

- Creates an annotated tag named **`v1.0`** for the current commit.
- **`-a`:** Specifies that the tag is annotated.
- **`v1.0`:** The naeof the tag.
- **`-m "Version 1.0 release"`:** A message describing the tag's purpose.

#### 2. Push the tag to the remote:

```bash
git push origin v1.0
```

- Uploads the specific tag (**`v1.0`**) to the remote repository.
- Tags are not automatically pushed to the remote when you push commit. They must be pushed explicitly using **`git push origin <tag-name>`**.

### Task-14: Rewriting Commit Hsitory

#### Use interactive rebase to modify commit messages:

```bash
git rebase -i HEAD`3
```

- Opens an interactive rebase session for the last 3 commits (**`HEAD~3`**).
- You can choose to edit commit messages, squash commits, or reorder them.

### Task-15: Cherry-Picking Commits

#### 1. Apply a specific commit to another branch:

```bash
git cherry-pick <commit-hash>
```

- Applies the changes from the commit identified by __`<commit-hash>`__ to the current branch.

---

## Part 6: Collaboration

### Task-16: Forking and Pull Request

#### 1. Fork a repository and colne it locally:

```bash
git clone https://github.com/your-username/forked-repo.git
```

- Go to the repository you want to contribute to on GitHub.
- Click the Fork button (usually at the top-right of the page).
- This creates a copy of the repository under your GitHub account.
- Copies the forked repository from your GitHub account to your local machine.
- You can now make changes locally.

#### 2. Make changes and push

```bash
git checkout -b fix-typo
echo "Typo fixed" >> README.md
git commit -m "Fixed a typo"
git push origin fix-typo
```

- Create a new branch and switch to it.
- make a change in that file.
- Commit the change with message.
- Push the local repository to reote repository.

#### 3. Open a pull request:

- Go to your forked repository on GitHub.
- You'll see a notification: __"Recently pushed branches: fix-typo. Compare & pull request."__
- Click __"Compare & pull request"__.
- Fill in the pull request details (title and description of your changes).
- Submit the __pull request__.

### Task 17: Simulating Team Collaboration

#### 1. Simulate a conflict by having two users modify the same file.

#### 2. Practice resolving the conflict as a team.

---

## Part 7: Ignoring Files

### Task-18: Using .gitignore

#### 1. Create `.gitignore` file:

```bash
echo "node_modules/" > .gitignore
git add .gitignore
git commit -m "Added .gitignore"
```

- __`echo "node_modules/" > .gitignore`:__
  - Creates a file named __`.gitignore`__ in your repository.
  - Adds a rule to ignore the __`node_modules/`__ directory (commonly used in JavaScript projects for dependencies).
- __`git add .gitignore`:__
  - Stages the __`.gitignore`__ file so it can be committed to the repository.
- __`git commit -m "Added .gitignore"`:__
  - Commits the __`.gitignore`__ file to the repository, making it part of your project's version control.

#### 2. Verify that ignored files are not staged:

```bash
git status
```

- Shows the status of your repository, including any staged or untracked files.
- The __`node_modules/`__ directory (and any files matching patterns in __`.gitignore`__) will not appear in the list of files to be staged.

---

## Part 8: Automation and Cleanup

### Task-19: Cleaning the Repository

#### 1. Remove untracked files:

```bash
git clean -f
```

- __`git clean`:__
  - Remove untarcked files and directories from the working directory.
  - Does not affect tracked files (files already added to Git).
- __`-f`:__
  - The __`-f`__ flag is required to force the removal of untracked files. By default, Git prevents accidental deletion of files, so the __`-f`__ flag ensures that you intentionally clean your repository.

### Task-20: Aliases and Shortcuts

#### 1. Create an alias for frequently used commands:

```bash
git config --global alias.st status
git config --global alias.cm commit
```

- __`git config --global alias.st status`:__
  - Creates an alias __`st`__ that runs __`status`__.
  - After this, you can type __`git st`__ instead of __`git status`__.

- __`git config --global alias.st commit`:__
  -  Creates an alias cm that runs __`commit`__.
  - After this, you can type __`git cm`__ instead of __`git commit`__.

#### 2. Use the alias:

```bash
git st
git cm -m "Message"
```

- __`git st`:__
  - Executes the same functionality as __`git status`__.
  - Executes the same functionality as __`git commit -m "Message"`__.

---
