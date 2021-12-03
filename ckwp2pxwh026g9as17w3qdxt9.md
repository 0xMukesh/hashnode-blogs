## ✨Understanding the different stages in Git

Hey everyone 👋, Welcome to the second part of Git crash course 

If you haven't checked out part 1, here is the  [link](https://kirablog.hashnode.dev/git-crash-course)

So let's get into the ✨ m a g i c a l ✨ world of Git

### Different stages of a file in a Git

1) **untracked** - You have created a new file called `magicofgit.txt`.

This file is now in `untracked` state.

2) **staged** - You executed `git add magicofgit.txt` command.

Now this file is in `staged` state.

3) **committed** - You executed `git commit -m "Exploring the magic of Git"` 

Now this file is in `committed` state.

4) **modified** - You have add the text `Hello, World` in `magicofgit.txt` file

Now this file is in `modified` state.

#### The four areas in Git

Git stores your data in these four areas:

- Working directory
- Staging area
- Repository
- Stash

**Working directory** - When a file is `untracked` or `modified`, it's changes are present in the working directory.

**Staging area** - When a file is `staged`, it's changes are present in the staging area.

**Repository** - When changes in a file are committed , it's stored in the repository.

**Initialize a new git repository**

Let's create a new folder named `Exploring Git`. Now let's initialize a empty git repository using the following command 

```bash
git init
```

At the current moment, all the four areas would be empty as there are no files in our git repository.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1638526886183/c5n9mtSPo.png)

#### Adding contents to our Git repository

Let's create a new text file named `magicofgit` and adding the below text to the file and saving it.

```
Hello, World
```

Now this file is an `untracked` file.

Let's check the status of our git repository by using `git status` command.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1638450170551/KHkc2sGhI.png)

Now the stages of git will look something like this.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1638527148754/xJee-IESZ.png)

#### Staging the files 

Let's stage the files, so that git can track them by using the below command 

```bash 
git add magicofgit.txt
```

If we check the status of our git repository, we should see something like this :

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1638450680582/5jldYMCoV.png)


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1638527835824/WDe9Ut1U_.png)


#### Committing the files

Let's commit the staged files into our git repository by using the below command 

```bash 
git commit -m "Committed the staged files into the git repository"
```

> **What is a commit?** : 
> A commit records the changes that were staged when the commit was made. In this case, the > changes that this commit recorded are
> - Creation of the `magicofgit.txt` .
> -  Adding the `Hello, World` to the text file.

To view the commit history, we can use `git log`.

![WpBk1xf14c.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1638527722616/v6akzdX4O.png)

> `56d398f...` is known as `commit hash`. Each commit in a repository has it's unique commit hash


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1638527942614/zx4xGA5qA.png)

#### Merging a branch into the master branch

Let's create a branch called `gitBranch`, using the below command :

```bash
git branch gitBranch
```
Let's now checkout to the `gitBranch` and make few changes in the text file.

To checkout to the `gitBranch` branch, we will use the below command 

```bash 
git checkout gitBranch
```

Let's add a new line in the text line, with the content as `Hello, Hashnode` and saving the file.

This puts the text file into the `modified` state. 

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1638453189154/aJxliAX_J.png)

Let's stage the modified text file. The text file is unstaged as the `untracked` and `modified` change's are present in the working directory.

So let's quickly stage this modified text file by using the below command :

```bash 
git add magicofgit.txt
```

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1638528303386/Xe-7idLf_.png)

Let's commit our staged file as well by using the below command :

```bash 
git commit -m "Hello, from gitBranch"
```

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1638528261524/wHyJhdNlu.png)

Now let's merge this branch into the master branch. To do that, first we have to checkout to the master branch, by using the below command :

```bash 
git checkout master
```

After we are in the master branch, we can merge the `gitBranch` branch by using the below command :

```bash 
git merge gitBranch
```

If we check the content of the text file now, it will have a new line saying `Hello, Hashnode`

🎉 Yay! You have successfully merged the `gitBranch` branch.

#### Stashing

Let's create a new branch named `stash` by using the below command :

```bash 
git branch stash
```

Let's checkout to the `stash` branch by using the below command :

```bash 
git checkout stash
``` 

Let's add a new line to text file in `stash` branch saying `This is the line which taught me stashing` and let's save it.

Let's staged this modified text file by using the below command :

```bash
git add magicofgit.txt
```

Wait you remember that there is some urgent in the `master` branch, but if you checkout to `master` branch you are going to lose the modifications which you have made in the current branch.

To avoid this happening we could use a cool feature in git ✨s t a s h✨.

> Stash is a place where you can temporarily save uncommitted files both in the working directory and the index. 

You could place your staged files in stash by using the below command :

```bash 
git stash
```


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1638528520559/wSQ4PnAxG.png)

After you have completed your work in the `master` branch, you could use `git stash pop` to get the stashed items. 


🎉 Yay! You have successfully learnt the different stages in Git, give a pat to yourself

