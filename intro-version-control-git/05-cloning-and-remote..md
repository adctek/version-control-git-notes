# Cloning Repositories

Cloning created a full copy of nearly all data that the original repository has.

The following command below creates a directory named `some-project`, initializes a `.git` directory inside it, pulls down all the data for that repository, and checks out a working copy of the latest version.

```bash
git clone https://github.com/github-user/some-project

Cloning into 'some-project'...
remote: Reusing existing pack: 1723, done.
remote: Total 1723 (delta 0), reused 0 (delta 0)
Receiving objects: 100% (1723/11), 274.31 KiB | 186.00 KiB/s, done.
Resolving deltas: 100% (632/632), done.
Checking connectivity... done.

```

To clone the repository into a directory with a different name, then specify the name as an argument

```bash
git clone https://github.com/github-user/some-project new-folder-name

Cloning into 'new-folder-name'...
.
.
.

```

# Working with Remotes

# Showing remotes

To list the shortnames of each remote handle use `git remote`

```bash
git clone https://github.com/github-user/some-project

Cloning into 'some-project'...
.
.
.

cd some-project

git remote
origin
```

`origin` is the default name Git gives to a server from which a repo has been cloned.


To show the URLs that Git has stored for the shortname to be used when reading and writing to that remote:

```bash
git remote -v

origin	https://github.com/github-user/some-project (fetch)
origin	https://github.com/github-user/some-project (push)
```

## Adding Remote Repositories

The `git clone` command implicitly adds the `origin`remote. To add a new remote explicitly:

```bash
git remote add agu https://github.com/another-github-user/some-project

git remote -v

origin	https://github.com/github-user/some-project (fetch)
origin	https://github.com/github-user/some-project (push)
agu 	https://github.com/another-github-user/some-project (fetch)
agu 	https://github.com/another-github-user/some-project (push)
```

## Fetch from Remotes

To get data from the remote projects:

```bash
git fetch <remote>
```

`git fetch origin` will fetch any new work that has been pushed to that server since you cloned (or last fetched from). No merge is done.

## Pushing to Remotes

To share the project and push it upstream:

```bash
git push <remote> <branch>
```

For instance:

```bash
git push origin master
```