## ✨ Git crash course

### What is Git ? 

Git is most widely used version control system. Git is originally developed in 2005 by Linus Torvalds, the creator of the famous kernel, Linux.

There are staggering number of software projects which reply on Git on daily basis.

### Git Installation 

Download the  [latest version of Git](https://git-scm.com/downloads) for your OS.

### Git Setup

After you have installed Git, the first thing that is to do is set your user name and email address.

To setup your user name and email address using the following commands 

```bash 
git config --global user.name "your name"
git config --global user.email youremail@example.com
```
### Git Commands

As we have successfully setup Git, let's talk about the commands in Git

#### 1) Git init

This initializes an empty repository locally on your computer.

```bash 
git init
```

#### 2) Git status 

This command shows which files are added to the staging area (More about the different stages of a file in Git in the next post) and which are left to be added. 

```bash
git status
```

#### 3) Git add 

This adds the files from your working tree into the staging area.

```bash
git add -A #Adds all the files into the staging area [Stage all (new, modified, deleted) files] 
git add . #Adds all the files into the staging area [Stage all (new, modified, deleted) files]
git add --ignore-removal #Doesn't add deleted files [Stage new and modified files only]
git add -u #Doesn't add new files [Stage modified and deleted files only]
git add index.js #Adds only index.js file into the staging area
```

#### 4) Git commit 

> **What's a commit?**:
A commit records the changes that were staged when the commit was made. In this case, the changes that this commit recorded are

> - Creation of `index.js`
> - Adding some cool JavaScript code into `index.js`

`git commit` commits the files changes and helps you keep track of your code. 

```bash 
git commit -m "your message" 
git amend -amend -m "your edited commit message" #Updates the commit message"
```

#### 5) Git push 

This command is used to push your code to a Git provider like GitHub.

```bash 
git push 
```

#### 6) Git clone 

If you want to clone a whole repository from Git provider like GitHub, then do the following

Go the repository, which you want to clone, click on the button which says `Code`. That should show a dropdown something like this


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1638443558987/fBPGJrt8w.png)

Copy the URL and run the following command 

```bash 
git clone https://github.com/Kira272921/portfolio.git #Change the URL with the one which you have copied
```

#### 7) Git branch

A Git branch is an brand new working directory, staging area, and project history.

**Create a new branch**

```bash
git branch branch-name
```

**Get list of all the branches**

```bash 
git branch
```

OR

```bash 
git branch --list
```

**Delete a branch**

```bash 
git branch -d branch-name
```

**Rename a branch**

```bash 
git branch -m old-branch-name new-branch-name
```

#### 8) Git checkout

This allows you to switch between branches

```bash
git checkout branch-name
```

#### 9) Git merge

This allows you to merge a branch with the currently active branch (the branch which you are currently in) with any available branch

```bash
git merge branch-name
``` 

🎉 Yay! You have completed the crash course on Git.

I will be releasing courses on Git's different stages of a file and individual Git commands in the future, so stay tuned.
