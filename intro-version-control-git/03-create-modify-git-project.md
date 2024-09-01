# Create and modify a project

## Set up your Git repository

1. Create a folder for the project.
   
   ```bash
   mkdir project
   ```

2. Change to the project directory
   
   ```bash
   cd project
   ```
   
3. Initialize repository and set the name of the default branch to main
   
   ```bash
   git init --initial-branch=main

   Initialized empty Git repository in /home/<user>/project/.git/
   Switched to a new branch 'main'
   ```
   
4. Show the status of the working tree
   
   ```bash
   git status

   On branch main
   No commits yet
   nothing to commit (create/copy files and use "git add" to track)
   ```

## Stage a file

1. Create a new file in gthe project folder.
   
   ex: *index.htnl* 
   
2. Get the status of the working tree
   
   ```bash
   git status

   No commits yet
   Untracked files:
     (use "git add <file>..." to include in what will be committed)
         index.html

   nothing added to commit but untracked files present (use "git add" to track)
   ```
3. Add the new file to Git's index
   
   ```bash
   git add .
   ```
      
4. Get the status of the working tree
   
   ```bash
   git status

   On branch main
   Initial commit
   Changes to be committed:
     (use "git rm --cached <file>..." to unstage)
         new file:   index.html
   ```

## Make a commit

1. Use the following command to create a commit
   
   ```bash
   git commit index.html -m "Create index.html file"

   [main (root-commit) 87e874c] Create index.html file
   1 file changed, 0 insertions(+), 0 deletions(-)
   create mode 100644 index.html
   ```

2. Show information about the commit
   
   ```bash
   git log

   commit 87e874c4aeeb3f9692ae5d9875235353708d7dd5
   Author: User Name <user-name@domain.com>
   Date:   Fri Aug 28 15:37:05 2024

   Create index.html file
   ```

   
## Track changes in Git

1. Modify the file and save.
   
2. Verify what changed
   
   ```bash
   git diff
   ```
   It will show all the changes that haven't been staged.

3. Commit the change. Instead of using the -a flag, you can explicitly name a file to be staged and committed if Git already has the file in the index.
   
   ```bash
   git commit -m "Add HTML code to index.html" index.html
   ```

## Ignore files

1. Create and open a file named .gitignore
2. Add the following lines to the file:
   
   ```bash
   *.bak
   *~
   ```

   `.gitignore`is a very important file in the Git world because it prevents extraneous files from being submitted to version control.

   `.gitignore` files are available for popular programming environments and languages.

3. Save and commit the changes
   
   ```bash
   git add -A
   git commit -m "Ignore editor backups"
   ```

   Use the `-A` option with `git add` to add all untracked (and not ignored) files, and the files that have changed.

## Recover deleted files

In the case of a file deleted from the operating system

1. File deleted using `rm` command
   
   ```bash
   rm index.html
   ```

2. File can be recovered from Git
   
   ```bash
   git checkout -- index.html
   ```

In the case of a file deleted from Git

1. File deleted using `git rm` command
   
   ```bash
   git rm index.html
   ```

2. File cannot be directly recovered using `git checkout`
   
   ```bash
   git checkout -- index.html

   error: pathspec 'index.html' did not match any file(s) known to git.
   ```

3. Need to unstage the deletion
   
   ```bash
   git reset HEAD index.html

   Unstaged changes after reset:
   D       index.html
   ```
   
4. Now the file can be recovered
    
   ```bash
   git checkout -- index.html
   ```


## Revert a commit

1. Replace the contents of index.html.
   
2. Save and close the file.
   
3. Commit the changes
   
   ```bash
   git commit -m "Purposely overwrite the contents of index.html" index.html
   ```

4. Show the latest commit
   
   ```bash
   git log -n1
   ```

5. In this case using `git checkout` will still show the latest version. use git revert to undo your committed changes
   
   ```bash
   git revert --no-edit HEAD
   ```
   The `--no-edit` flag indicates no commit message for this action.
   ```bash
   [main 6a27310] Revert "Purposely overwrite the contents of index.html"
   1 file changed, 13 insertions(+), 1 deletion(-)
   ```

6. show the latest commit
   
   ```bash
   git log -n1

   Author: User Name <user-name@contoso.com>
   Date:   Sat Aug 31 00:42:26 2024

   Revert "Purposely overwrite the contents of index.html"

   This reverts commit 15d3bded388470c98881a632025bc15190fe9d17.
   ```


