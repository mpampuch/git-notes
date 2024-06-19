# git-notes

## Resetting commits

![.](resetting/resetting-1.png)

`--soft`: Removes the commit

![.](resetting/resetting-2.png)


`--mixed`: Removes the commit and unstages files

![.](resetting/resetting-3.png)

`--hard`: Removes the commit, unstages files, and discards the local changes

![.](resetting/resetting-4.png)


## Working on a forked repository

1. Fork a remote repository for an open source project and clone it on your local machine 

![.](forking/forking-1.png)

- This forked repository is not connected to the original repository, so from time to time, it can become out of sync with the original repository. If other people contribute to the base repository and add new commits to the main branch, you are not going to be aware of those new commits.

To fix this and keep the forked repository up to date:

2. In the local repository you have a reference to the forked repositrory called `origin`. Add another reference to the original repository called `base`.

![.](forking/forking-2.png)


3. Pull the commits from the `base` repository and then push them to the forked (`origin`) repositroy.

![.](forking/forking-3.png)

## Collaborative Workflow Best Practices

### Step 1: Check remote directory

A remote is a shared Git repository that allows multiple collaborators to work on the same Git project from different locations.
To view the remote directory, type

```bash
git remote -v
```

If remote directory has never been added to your local directory, use the following command

```bash
git clone remote_location clone_name
```
Otherwise, move onto step 2

### Step 2: Fetch changes from the remote

```bash
git fetch
```
In Git, the git fetch command downloads objects from the origin remote repository.
The changes, however, are not merged into the current branch-name branch. 
Instead, they are stored in the origin/branch-name branch, waiting to be merged.

#### Example:

```bash
git branch -a
* master
 
git fetch
remote: Counting objects: 5, done.
remote: Compressing objects: 100% (5/5), done.
remote: Total 5 (delta 1), reused 0 (delta 0)
Unpacking objects: 100% (5/5), done.
From /home/ccuser/workspace/curriculum-a/science-quizzes
 * [new branch]      master     -> origin/master
 
git branch -a
* master
  remotes/origin/master
```

In the provided example, using the git branch -a command to see the existing branches, you can see that fetched data has been stored in a new origin/master branch.

### Step 3: Merge changes from the remote

```bash
git merge origin/branch-name
```

### Step 4: Create a branch to work on a new project feature and switch over to that branch

```bash
git branch new-branch
git switch new-branch
```

### Step 5: Develop the feature on a branch and commit the work

```bash
git add files
git commit -m "message"
```

### Step 6: Fetch and merge from the remote again (in case new commits were made)

```bash
git fetch
git merge origin/branch-name
```

Steps 2 and 6 are a safeguard against merge conflicts, which occur when two branches contain file changes that cannot be merged with the git merge command.

### Step 7: Push branch up to the remote for review

```bash
git push origin branch-name
```

### Step 8: Switch back to main branch and delete new branch (if new feature is fully complete)

```bash
git switch main
git branch -D branch-name
```

