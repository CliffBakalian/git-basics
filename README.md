## GIT Basics

This is a repo for learning git basiscs for CMSC330 at UMD. I would reccomend you to make a new repository and trying these commands there. You are still welcome to use this repo if you really want. You can also read the corresponding notes at [https://bakalian.cs.umd.edu/330](https://bakalian.cs.umd.edu/330)

### Cloning
To copy this code onto your local machine for the first time, you can run
```bash
git clone git@github.com:cliffbakalian/git-basics.git
```
if you are cloning via ssh.
This will make a directory called `git-basics` with this file in it.

### Committing
Once you have cloned the repo, you can edit this file and then track your changes.To start you need to first add this file to the staging area:
```bash
git add README.md
```
Once you have added the file to the staging area, you can then take a snapshot with the `commit` command. 
```bash
git commit -m "my first edit"
```
The `-m` flag allows you to write a quick message describing the change you made. You must always add a comment when you commit.

### Publishing to the world
Once you made your edit and want your changes to be publicly seen, you can push your changes to the internet:
```bash
git push
```

If you owned this repository or had edit access the change could then been automatically seen by everyone as the newest version of this README. I can't give everyone write access but that does not mean your change cannot be seen. When you push to someone else's repo, you create something called a pull request. You can go to [https://github.com/CliffBakalian/git-basics/pulls](https://github.com/CliffBakalian/git-basics/pulls) to see them all. Should I want to, I can accept your pull request and then it becomes part of the offical version. 

### Getting updates
This is the one step where you have to use your own repo to get the most out of it. If this repo ever changed after you cloned it, you can copy the changes over from your local machine using the `pull` command. 
```bash
git pull
```

The best way to see this in action is to edit a file in your repository deirectly on GitHub, commiting on the website and then `pull`ing those changes to your local machine. 

### Reverting a Change
Suppose you made a mistake or got lost and need to go to a previous version of your code. You can do go easily with Git. 
First you need to figure out what the name of the snapshot you want to reset to. 
```bash
git log
```
This should list a history of all the commits. Each commit's ID is a long hash string. You can identify snapshots by the message you used when you commited it (you did use meaningful messages, right?).

Once you have the ID (hash string) you can run the following command
```bash
git revert <commit-id>
```
If you had not commited your work before hand, git will ask if you want to save your work before undoing everything. You can save your work by commiting or by stashing it (`git stash`) in local memory. Stashing does not keep your edits in memory for long so I would reccomend just commiting.

Reverting will then add a new snapshot that is a copy of a previous snapshot. To get rid of the commit history you probably want to look into reseting ([https://git-scm.com/docs/git-reset](https://git-scm.com/docs/git-reset)). Reseting is dangerous and I would use it only in emergencies.
