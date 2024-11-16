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
- __`Git Config`:__
  - It is a git command which is use to view __configuration option__ for git.
  - It can adjust settings on Three Levels:
    -  __System Level:__ Limits to user computer device.
    - __Global Level:__ Its applies to user account running the command.
    - __Local Level:__ Specific to the repository wher the command run.
####
- __`--global`:__
  - It means that the settings will apply globally for the current user on the system.
####
- __`user.name`:__
  - This is the configuration key being set and it determines the name associated with git commits. When you commit changes to a repository, Git uses this name as part of the commit metadata.
####
- __`"Your Name"`:__
  - This will assign the value to `user.name` key. It will appear in the commit logs.
####
- __`user.email`:__
  - Similar as `user.name` but its specific with email address to be associated with git commits.
####
- __`"Your-email@exmaple.com"`:__
  - Thsi will assign `user.email` key to appear in a git commit.
###
#### 2. View  your Git Configuration:
###
```bash
git config --list
```
####
- __`--list`:__
  - Lists __all configurations__ from all levels: system, global, and local, in order of precedence (local > global > system).
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
- __`mkdir MyProject`:__
  - It create __New Directory__ with named `MyProject` to the current location.
  - __`mkdir`:__ stands for __Make Directory__.
  - __`MyProject`:__ is the name of directory is created.
####
- __`cd MyProject`:__
  - Changes the current working directory to `MyProject`.
  - __`cd`:__ stands for __Change Directory__.
  - __`MyProject`:__ is the name of the folder to move in.
###
#### 2. Initialize it as a Git repository:
###
```bash
git init
```
####
- __`git init`:__
  -  __Initializes a new Git repository__ in the current directory. It sets up the necessary files and folders to start __tracking changes__ to your project's files using Git.
  - When you run `git init`, a __hidden directory named `.git`__ is created in the current folder.
  - This directory contain __metadata and objects git__ needs to manage the repository.
###
### **Task-3: Create a File and Make Multiple Commits**
###
#### 1. Create a new file and add content:
###
```bash
echo "My First Project" > README.md
```
####
- __`echo "My First Project"`:__ 
  - Its a command which is use to __print output__ the text __`"My First Project"`__ to a file.
####
- __`>`:__ 
  - This is a __output redirection operator__.
  - It takes the output of the __`echo`__ command and writes it to the specified file(__`README.md`__).
  - If the file deos not exist, it will created. If does exist, its contents will be replaced with the new output.
####
- __`README.md`:__
  - This is the __target file__ where the output (__`"My First Project"`__) will be __saved__.
-The __`.md` extension__ stands for __Markdown__, a common file format for documentation.
###
#### 2. Stage the file:
###
```bash
git add README.md
```
####
- __`git add README.md`:__
  - Adds the file __`README.md`__ to the staging area in Git.
  - The __Staging area__ is where the __changes__ are prepared to __committed__.
###
### 3. Commit the file:
###
```bash
git commit -m "Initial commit: Added README.md"
```
####
- __`git commit`:__
    - Finalize changes in the __staging area__ by creating a __new commit__ in the repository.
- __`-m`:__
  - Allow you to specify a __commit message__ directly in the command.
- __`"Initail commit: Added README.md"`:__
  - This is the __commit message__. Its describes the __changes being commited__.
  - Good messages explain what And why a change was made.
###
#### 4. Make changes to the file:
###
```bash
echo "Added a description" >> README.md
```
####
