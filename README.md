# git-notes

## Resetting commits

![.](resetting/resetting-1.png)
![.](resetting/resetting-2.png)
![.](resetting/resetting-3.png)
![.](resetting/resetting-4.png)

- `--soft`: Removes the commit
- `--mixed`: Removes the commit and unstages files
- `--hard`: Removes the commit, unstages files, and discards the local changes

## Working on a forked repository

1. Fork a remote repository for an open source project and clone it on your local machine 

![.](forking/forking-1.png)

- This forked repository is not connected to the original repository, so from time to time, it can become out of sync with the original repository. If other people contribute to the base repository and add new commits to the main branch, you are not going to be aware of those new commits.

To fix this and keep the forked repository up to date:

2. In the local repository you have a reference to the forked repositrory called `origin`. Add another reference to the original repository called `base`.

![.](forking/forking-2.png)


3. Pull the commits from the `base` repository and then push them to the forked (`origin`) repositroy.

![.](forking/forking-3.png)