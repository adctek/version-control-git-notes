# Working with branches

## Creating a New Branch

Creating a new branch simply creates a new pointer to the same commit you’re currently on.

To create a new branch called *"feature"*:

```bash
git branch feature
```

## Switching Branches

To switch to the *"feature"* branch:

```bash
git checkout feature
```

This moves HEAD to point to the *"feature"* branch.

Note that when you switch branches in Git, files in your working directory will change. If you switch to an older branch, your working directory will be reverted to look like it did the last time you committed on that branch.

To create a new branch and switch to it at the same time:

```bash
git branch -b feature
```

### Using `git switch` command (Git version 2.23 onwards)

Switch to an existing branch:

```bash
git switch feature-branch
```

Create a new branch and switch to it:

```bash
git switch -c feature-branch.
```

Can also use the full flag: `--create`.

Return to previously checked out branch:

```bash
git switch -
```

## Basic Merging

Once all the changes to the feature-branch are complete and commited, they can be merged to the master/main branch.

First switch to the master/main branch

```bash
git checkout master
```

Then merge the feture-branch

```bash
git merge feature-branch

Updating f42c576..3a0874c
Fast-forward
 index.html | 2 ++
 1 file changed, 2 insertions(+)
```

    
## Merge Conflicts

If the same part of the same file is modified differently in the two branches being merged, Git won’t be able to merge them cleanly. 

```bash    
git merge feature-branch

Auto-merging index.html
CONFLICT (content): Merge conflict in index.html
Automatic merge failed; fix conflicts and then commit the result.
```

To see which files are unmerged at any point after a merge conflict:

```bash
git status

On branch master
You have unmerged paths.
  (fix conflicts and run "git commit")

Unmerged paths:
  (use "git add <file>..." to mark resolution)

    both modified:      index.html

no changes added to commit (use "git add" and/or "git commit -a")
```

After fixing the conflicts and verifing that everything that had conflicts has been staged, use `git commit` to finalize the merge commit.
    

## Deleting a Branch

After your work is merged in, you have no further need for feature-branch, ad can be deleted:

```bash
git branch -d feature-branch
```

