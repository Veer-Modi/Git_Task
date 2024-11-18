# Git And GitHub

## **Part-1: Introduction to Version Control and Git**

###

### **Task-1: Install and Configure Git**

###

#### 1. Configure Git your username and email:

###

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

####

- **`Git Config`:**
  - It is a git command which is use to view **configuration option** for git.
  - It can adjust settings on Three Levels:
    - **System Level:** Limits to user computer device.
    - **Global Level:** Its applies to user account running the command.
    - **Local Level:** Specific to the repository wher the command run.

####

- **`--global`:**
  - It means that the settings will apply globally for the current user on the system.

####

- **`user.name`:**
  - This is the configuration key being set and it determines the name associated with git commits. When you commit changes to a repository, Git uses this name as part of the commit metadata.

####

- **`"Your Name"`:**
  - This will assign the value to `user.name` key. It will appear in the commit logs.

####

- **`user.email`:**
  - Similar as `user.name` but its specific with email address to be associated with git commits.

####

- **`"Your-email@exmaple.com"`:**
  - Thsi will assign `user.email` key to appear in a git commit.

###

#### 2. View your Git Configuration:

###

```bash
git config --list
```

####

- **`--list`:**
  - Lists **all configurations** from all levels: system, global, and local, in order of precedence (local > global > system).

###

### **Task-2: Initialize a Repository**

###

#### 1. Create a new project folder and navigate to it:

###

```bash
mkdir MyProject
cd MyProject
```

####

- **`mkdir MyProject`:**
  - It create **New Directory** with named `MyProject` to the current location.
  - **`mkdir`:** stands for **Make Directory**.
  - **`MyProject`:** is the name of directory is created.

####

- **`cd MyProject`:**
  - Changes the current working directory to `MyProject`.
  - **`cd`:** stands for **Change Directory**.
  - **`MyProject`:** is the name of the folder to move in.

###

#### 2. Initialize it as a Git repository:

###

```bash
git init
```

####

- **`git init`:**
  - **Initializes a new Git repository** in the current directory. It sets up the necessary files and folders to start **tracking changes** to your project's files using Git.
  - When you run `git init`, a **hidden directory named `.git`** is created in the current folder.
  - This directory contain **metadata and objects git** needs to manage the repository.

###

### **Task-3: Create a File and Make Multiple Commits**

###

#### 1. Create a new file and add content:

###

```bash
echo "My First Project" > README.md
```

####

- **`echo "My First Project"`:**
  - Its a command which is use to **print output** the text **`"My First Project"`** to a file.

####

- **`>`:**
  - This is a **output redirection operator**.
  - It takes the output of the **`echo`** command and writes it to the specified file(**`README.md`**).
  - If the file does not exist, it will created. If does exist, its contents will be replaced with the new output.

####

- **`README.md`:**
  - This is the **target file** where the output (**`"My First Project"`**) will be **saved**.
    -The **`.md` extension** stands for **Markdown**, a common file format for documentation.

####

- **Output:**

```mathemetica
My First Project
```

###

#### 2. Stage the file:

###

```bash
git add README.md
```

####

- **`git add README.md`:**
  - Adds the file **`README.md`** to the staging area in Git.
  - The **Staging area** is where the **changes** are prepared to **committed**.

###

### 3. Commit the file:

###

```bash
git commit -m "Initial commit: Added README.md"
```

####

- **`git commit`:**
  - Finalize changes in the **staging area** by creating a **new commit** in the repository.
- **`-m`:**
  - Allow you to specify a **commit message** directly in the command.
- **`"Initail commit: Added README.md"`:**
  - This is the **commit message**. Its describes the **changes being commited**.
  - Good messages explain what And why a change was made.

###

#### 4. Make changes to the file:

###

```bash
echo "Added a description" >> README.md
```

####

- **`echo "Added a description"`:**
  - **Output** the text **`Added a description`**.

####

- **`>>`:**
  - **Redirects** the output to a file and **appends it**.
  - If the file doesn't exist, it will create the file.

####

- **`README.md`:**
  - The **target file** where the text will be **appended**.
- **Output:**

```mathematica
My First Project
Added a description
```

###

#### 5. Stage and Commit te changes:

###

```bash
git add README.md
git commit -m "Updated README with a description"
```

####

- **`git add README.md`:**
  - Stages the updated **`README.md`** file so that Git can include it in the next commit.
  - After appending new content to **`README.md`**, the file is modified.
  - **Track the changes** made to **`README.md`** and prepare it for the **next commit** by placing it in the **staging area**.

####

- **`git commit -m "Updated README.md with a description"`:**
  - Saves the staged changes (e.g., the updated **`README.md`** file) into the Git repository as a new commit. This records the modifications in the project's history.

###

### Task-4: Check Status and log:

###

#### 1. Check the repository's current status:

###

```bash
git status
```

####

- **`git status`:**
  - Display the **current state** of the **working directory and staging area** in your Git **repository**.
  - Helps you see which **changes** have been made, which are **staged for commit**, and which are **not yet tracked** by Git.

###

#### 2. View commit history in detail:

###

```bash
git log --online --graph --decorate
```

####

- **`git log`:**
  - Displays the **commit history** of your repository.

####

- **`--online`:**
  - **Formats each commit** as a single line for a **cleaner** and more **concise view**.
  - Shows only the **commit hash** (shortend) and the **commit message**.

####

- **`--graph`:**
  - Adds a **visual representation** of the **commit history** as a **text-base graph**.
  - Useful in repository with **branches and merges**, as it shows how branches **diverge and rejoin**.

####

- **`--decorate`:**
  - Displays **references alongside** their respective commits.
  - Makes it to see where **branches or tags point** in the **commit history**.
  ####
- **Output:**

```mathematica
* 2f8d6a2 (HEAD -> main) Updated README with a description
* d3c4b21 Initial commit: Added README.md
```

###

### Task-5: Creat and Clone a Repository

###

#### 1.Create a repository on Github named `example-repo`:

###

- Create a new repository in Github.

###

#### 2. Clone it locally:

###

```bash
git clone http://codinggita.com/example-repo
```

####

- **`git clone`:**
  - A Git command used to create a complete **copy repository** on **local machine**, including **Files and directories**, **Commit history**, **Branches**.

####

- **`http://condinggita.com/example-repo`:**
  - This is the **URL** of the **remote repository** you want to **clone**.

###

### Task-6: Understanding the Git Workflow

###

#### 1. Make changes to file in the working directory:

###

```bash
echo "Workflow example" > workflow.md
```

####

- This create a filed named **`workflow.md`** and **`"Workflow example"`** as its content.

###

#### 2. Stage the file:

###

```bash
git add workflow.md
```

#####

- This tell Git to track the file and prepares it for the next commit.

###

#### 3. Commit the file to the repository:

###

```bash
git commit -m "Added workflow example"
```

####

- **`-m "Added workflow example"`** provides a message describing the changes.

###

## Part-2: Workig with Repositories

###

### Task-7: Branching and Merging

###

#### 1. Create a branch for a feature:

###

```bash
git branch feature-login
git checkout feature-login
```

####

```bash
git checkout -b feature-login
```

####

- **`git branch`:**
  - To create new branch.

####

- **`feature-login`:**
  - **`feature-login`** Name of created branch.
  ####
- **`git checkout`:**
  - Switches to the **`feature-login`** branch.

####

- **`git checkout -b feature-login`:**
  - **`git checkout`** is used to switch branch.
  - **`-b`** to create new branch with named **`feature-login`**.

###

#### 2. Add a new file and commit changes:

###

```bash
echo "Login Page" > login.html
git add login.html
git commit -m "Added login page"
```

####

- **`echo "Login Page" > login.html`:**
  - Creates a new file named **`login.html`** in your working directory.
  - Writes the text **`"Login Page"`** into the file.
  - If the file already exists, this command overwrites its content.

####

- **`git add login.html`:**
  - Adds the file **`login.html`** to the staging area.\
  - This means Git is now **tracking the file** and preparing it for inclusion in the **next commit**.

####

- **`git commit -m "Added login page"`:**
  - **Creates a commit** with the **staged changes** (i.e., the **`login.html`** file).
  - **Saves the changes** to the **repository's history**.
  - The commit message (**`"Added login page"`**) describes what was done in this commit.

###

#### 3. Merge the feature branch into `main`:

###

```bash
git checkout main
git merge feature-login
```

####

- **`git checkout main`:**
  - It switches to **`main`** branch.

####

- **`git merge feature-login`:**
  - **`git merge`** is used to **merge two branches**.
  - **Combines the changes** made in the **`feature-login`** branch into the **`main`** branch.
  - This creates a **new commit** on **`main`** that includes the changes from **`feature-login`**.

###

### Task-8: Handling Merge Conflicts

###

#### 1. Create two branches:

###

```bash
git branch branch-A
git branch branch-B
```

####

- **`git branch branch-A`:**
  - Create a **new branch** with named **`branch-A`**.

####

- **`git branch branch-B`:**
  - Create a **new branch** with named **`branch-B`**.

###

#### 2. Modify the same line in `README.md` in both branches.

###

- Edit the file with some text in it.

###

#### 3. Merge `branch-A` into `main`:

###

```bash
git cheakout main
git merge branch-A
```

####

- This will merge **`branch-A`** into **`main`**.

###

#### 4. Attempt to merge `branch-B` into `main` (this will cause a conflict):

###

```bash
git merge branch-B
```

####

- Git **attempts to merge** the changes made in **`branch-B`** into the **`main`** branch.
- If the **same lines** in **`README.md`** were modified differently in **`branch-A`** and **`branch-B`**, a **merge conflict will occur**.

###

#### 5. Resolve the conflict manually in `README.md`, then:

###

```bash
git add README.md
git commit -m "Resolved merge conflict between branch-A and branch-B"
```

####

- **Open the file:**

```mathematica
<<<<<<< HEAD
This is branch-A content
=======
This is branch-B content
>>>>>>> branch-B
```

- **`<<<<<<< HEAD`:**
  - Shows the changes from the current branch (**`main`**, which now includes **`branch-A`**'s content).
- **`=======`:**
  - Separates the conflicting changes.
- **`>>>>>>> branch-B`:**
  - Shows the changes from **`branch-B`**.

####

- **Edit the file to resolve the conflict. For example:**

```plaintext
This is merged content from branch-A and branch-B
```

####

- **Save the file after resolving the conflict.**

####

- **`git add README.md`:**
  - Marks the conflict as resolved by staging the updated **`README.md`**.

####

- **`git commit -m "Resloved merge conflict between branch-A and breanch-B"`:**
  - **Finalizes the merge** by creating a **new commit** that includes the **resolved changes**.

###

### Task-9: Renaming and Deleting Branches

###

#### 1. Rename a branch:

###

```bash
git branch -m old-branch-name new-branch-name
```

####

- Renames an existing branch.
- **`-m`** stands for "move"(renaming the branch is treated as moving it to a new name).
- This works for both the branch you're currently on and other branches in the repository.

###

#### 2. Deleting a branch:

###

```bash
git branch -d feature-login
```

####

- its used to delete the branch.
- **`-d`** stands for **delete**.

###

### Part 3: Advanced Git Operations

###

### Task-10: Using Git Stach

###

#### 1. Make changes to a file but don't commit:

###

```bash
echo "Temporary work" >> temp.md
```

####

- Appends the text **`Temporary work`** to the file **`temp.md`**.
- These changes remain in the **working directory** (uncommitted and unstaged).

###

#### 2. Stach the changes:

###

```bash
git stach
```

####

- Temporarily saves the changes in a **"stash stack"** and reverts the working directory to a **clean state** (matching the last commit).
- Git takes the **modified files** and creates a **stash entry** that you can **retrieve later**.
- The changes are not committed but are saved for future use.

###

#### 3. View stached changes:

###

```bash
git stach list
```

####

- Lists all stashes saved in the stash stack.
- Git shows a **list of stash entries**, each with a **unique identifier** (e.g., **`stash@{0}`** for the **most recent stash**).
- **Output:**

```bash
stach@{0}: WIP on main: abc123 Initial commit
stach@{1}: WIP on main: def456 Added temp.md
```

###

#### 4. Apply the stached changes:

###

```bash
git stach apply
```

####

- Reapplies the **stashed changes** to the **working directory without removing** them from the **stash stack**.
- The most recent stash (e.g., **`stash@{0}`**) is applied to the current branch.
- The stash remains in the stack, so it can be reused if needed.

###

#### 5. Drop the stach after Applying:

###

```bash
git stach drop
```

####

- **Deletes** the **most recent stash** from the **stash stack**.
- The **most recent stash** (e.g., **`stash@{0}`**) is **permanently removed** from the **stack**.
- Once dropped, it cannot be recovered.

###

### Task-11: Rewritung History with Interactive Rebase

###

#### 1. Create multiple commits:

###

```bash
echo "Commit 1" > file1.txt && git add file1.txt && git commit -m "Commit 1"
echo "Commit 2" > file2.txt && git add file2.txt && git commit -m "Commit 2"
echo "Commit 3" > file3.txt && git add file3.txt && git commit -m "Commit 3"
```

####

- You now have three commits in your branch, each modifying a different file.
- **Commit 1:** Adds **`file1.txt`** with text **`"Commit 1"`**.
- **Commit 2:** Adds **`file2.txt`** with text **`"Commit 2"`**.
- **Commit 3:** Adds **`file3.txt`** with text **`"Commit 3"`**.

###

#### 2. Squash commits into one:

###

```bash
git rebase -i HEAD~3
```

- **`git rebase -i`:**
  - This is the command for starting an **interative rebase**.
- **`HEAD~3`:**
  - This specifies that you want to work with the last 3 commits (**`HEAD`** is the latest commit, and **`HEAD~3`** refers to the 3 most recent commits).
- This will open a text editor with a list of the last three commits, something like this:

```bash
pick <commit-hash-1> Commit 1
pick <commit-hash-2> Commit 2
pick <commit-hash-3> Commit 3
```

- Each line represents one commit, and **`pick`** means you want to keep that commit as is.
- To combine (or **squash**) the second and third commits into the first one, replace **`pick`** with **`squash`** (or **`s`**) for the second and third commits.

```bash
pick <commit-hash-1> Commit 1
squash <commit-hash-2> Commit 2
squash <commit-hash-3> Commit 3
```

- **`pick <commit-hash-1> Commit 1`:** Keeps the first commit as is.
- **`squash <commit-hash-2> Commit 2`:** Combines Commit 2 into Commit 1.
- **`squash <commit-hash-3> Commit 3`:** Combines Commit 3 into Commit 1.

###

### Task-12: Cherry-Picking Commits

###

#### 1. Create a new branch:

###

```bash
git checkout -b cherry-pick-exmple
```

####

- **`git checkout -b cherry-pick-example`:**
  - This creates a new branch named **`cherry-pick-example`** and checks it out.
  - You are now on the **`cherry-pick-example`** branch, ready to bring in changes from other branches.

###

#### 2. Cheery-pick a specific commit from another branch:

###

```bash
git cheery-pick <commit-hash>
```

####

- **`git cherry-pick`:**
  - This command allows you to pick a commit from another branch and apply it to the current branch.
- **`<commit-hash>`:**
  - This is the unique identifier (SHA) of the commit you want to cherry-pick. You can find the commit hash by using **`git log`** on the branch where the commit exists.

###

### Task-13: Tagging Commits

###

#### 1. Tag the commit:

###

```bash
git tag -a v1.0 -m "Version 1.0 release"
```

####

- **`git tag`:**
  - This command is used to create a tag.

####

- **`-a v1.0`:**
  - This creates an **annotated tag** named **`v1.0`**. Annotated tags are the most common type and contain metadata such as the tagger’s name, email, and date, in addition to the tag message.

####

- **`-m "Version 1.0 release"`:**
  - This option specifies a **message** for the tag, explaining what the tag represents (e.g., this is the release of version 1.0).

####

- This will create a tag **`v1.0`** that points to the current commit (the latest commit in your repository).

###

#### 2. Push the tag to the remote repository:

###

```bash
git push prigin v1.0
```

#####

- **`git push`:**
  - This command uploads your local commits and tags to the remote repository.
  ####
- **`origin`:**
  - This refers to the remote repository (the sefault name for the remote repository).
  ####
- **`v1.0`:**
  - This specifies the tag you want to push. In this case, the tag you created(**`v1.0`**).

###

### Task-14: Working with Remote repositories

###

#### 1. Add a remote repository

###

```bash
git remote add origin <repository-url>
```

####

- **`git remote add`:**
- This commamd is used to add a new remote repository to your project.

####

- **`origin`:**
  - This is the **default name** given to your remote repository. You can name it anything, but **`origin`** is most commanly used name for default remote repository.

####

- **`<repository-url>`:**
  - This is the **URL of the remote repository** where your code will be pushed.
###
### Task-15: Forking and Contributing
###
#### 1. Fork a repository on Github:
###
- Go to the GitHub repository you want to contribute to (e.g., an open-source project).
- Click the Fork button at the top right of the page.
- Choose your GitHub account to fork the repository into.
###
#### 2. Clone the fork locally:
###
```bash
git clone <repository-url>
```
#####
- __`git clone <forked-repo-url>`:__ 
  - This command clones the forked repository (not the original one) to your local machine. Replace __`<forked-repo-url>`__ with the URL of your fork (it will be something like __`https://github.com/your-username/repository-name.git`__).
- Once cloned, the repository will be available on your local machine, and you can start making changes.
###
#### 3. Create a new branch, make changes, and push:
###
```bash
git checkout -b fix-typo
echo "Typo fixed" >> README.md
git add README.md
git commit -m "Fixed a typo"
git push origin fix-typo
```
####
- __`git checkout -b fix-typo`:__ 
  - This command creates and switches to a new branch called __`fix-typo`__.
- It's important to use a descriptive name for the branch, indicating what the changes will be (e.g., __`fix-typo`__ for fixing a typo).
####
- __`echo "Typo fixed" >> README.md`:__
  - This command appends the text __`"Typo fixed"`__ to the __`README.md`__ file.
- You can make whatever changes are needed in your branch.
####
- __`git add README.md`:__
  - This stages the modified __`README.md`__ file, preparing it for the commit.
- __`git commit -m "Fixed a typo"`:__
  - This commits the changes, with the commit message __"Fixed a typo"__ to explain the change.
  ####
- __`git push origin fix-typo`:__
  - This uploads your __`fix-typo`__ branch to your remote fork (origin). Now your changes are saved in your forked repository on GitHub.
###
#### 4. Open a pull request on GitHub:
###
- Go to your forked repository on GitHub (where you just pushed the __`fix-typo`__ branch).
- GitHub will usually show a message like: __"Your branch is 1 commit ahead of `original-repo`: main"__ with an option to "Compare & pull request."
- Click on __Compare & pull request__.
- Provide a title and description for the pull request, explaining the changes you made (e.g., "Fixed a typo in __`README.md`__").
- Click __Create pull request__.