# Day 05 - Git and GitHub Basics



## Learning Goals



- Install and verify Git on Windows.

- Configure a Git username and private GitHub email.

- Clone a remote GitHub repository to the local computer.

- Understand the basic local Git workflow.

- Push a local commit to GitHub.

- Verify the uploaded changes on GitHub.



## Git and GitHub



- **Git** is a version-control tool installed on the local computer.

- **GitHub** is an online platform used to store and share Git repositories.

- A local change is not available on GitHub until it is committed and pushed.



## Core Workflow



1\. Modify or create a file.

2\. Use `git status` to check the repository status.

3\. Use `git diff` to review the changes.

4\. Use `git add` to move reviewed changes to the staging area.

5\. Use `git commit` to create a local snapshot.

6\. Use `git push` to upload the commit to GitHub.

7\. Verify the result on the GitHub repository page.



## Commands Practiced



```bash

git --version

git config --global user.name

git config --global user.email

git clone

git status

git diff

git add

git commit

git push

```



## Important Concepts



- **Working directory:** The local files currently being edited.

- **Staging area:** The reviewed changes selected for the next commit.

- **Commit:** A saved local snapshot with a descriptive message.

- **Remote repository:** The online version of the repository stored on GitHub.

- **Push:** Uploading local commits to the remote GitHub repository.

- **Clone:** Downloading a complete copy of a remote repository to the local computer.



## Troubleshooting Learned



- A browser being able to open GitHub does not always mean Git Bash can connect to GitHub.

- Git may require a separate proxy configuration when a VPN or proxy application is used.

- A new Windows user account requires Git identity settings to be configured again.

- Files that were pushed to GitHub can be recovered by cloning the repository again.

- Local files that were never committed and pushed may be lost if the local user profile is deleted.



## Employment Relevance



Git is commonly used by QA engineers to:



- Store test scenarios, bug reports, and automation code.

- Review changes before submitting work.

- Collaborate with developers through shared repositories.

- Maintain a clear history of testing documents and project updates.

