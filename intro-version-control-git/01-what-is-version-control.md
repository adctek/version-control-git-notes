# What is version control?

A version control system (VCS) is a program or set of programs that tracks changes to a collection of files.

Another name for a VCS is a software configuration management (SCM) system.

A VCS can be used for projects other than software, including books and online tutorials.

With a VCS, you can:
- See all the changes made to your project, when the changes were made, and who made them.
- Include a message with each change to explain the reasoning behind it.
- Retrieve past versions of the entire project or of individual files.
- Create branches, where changes can be made experimentally.
- Attach a tag to a version—for example, to mark a new release.

Git is a fast, versatile, highly scalable, free, open-source VCS. Its primary author is Linus Torvalds, the creator of Linux.

Git is a distributed version control. Project's complete history is stored both on the client and on the server.

# Git terminology

- **Working tree**: The set of nested directories and files that contain the project that's being worked on.

- **Repository (repo)**: The directory, located at the top level of a working tree, where Git keeps all the history and metadata for a project.

- **Hash:** A number produced by a hash function that represents the contents of a file or another object as a fixed number of digits. Git uses hashes that are 160 bits long.

- **Object**: A Git repo contains four types of objects:
    - A **blob** object contains an ordinary file.
    - A **tree **object represents a directory; it contains names, hashes, and permissions.
    - A **commit** object represents a specific version of the working tree.
    - A **tag** is a name attached to a commit.

- **Commit**: It means you are committing to the server the changes you have made so that others can eventually see them, too.

- **Branch**: A branch is a named series of linked commits.
    - The **default** branch created when you initialize a repository is called master or main.
    - The most recent commit on a branch is called the **head**.
    - The head of the current branch is named **HEAD**.

- **Remote:** Named reference to another Git repository.
    - **origin** is the default remote for push and pull operations.
