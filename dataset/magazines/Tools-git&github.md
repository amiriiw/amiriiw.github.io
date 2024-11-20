<h2 align="center">Git and Github</h2>
**<p align="center">learning URLs: <a href="https://faradars.org/courses/fvgit9609-git-github-gitlab">jadi github course</a></p>**

---

### What is Git?

**Git** is a distributed version control system that allows multiple developers to work on a project simultaneously without overwriting each other's changes. It tracks changes in files and helps coordinate work on those files among multiple people. With Git, you can keep a history of your project's evolution, revert to previous versions if needed, and create branches to work on new features independently.

---

### What is GitHub?

**GitHub** is a web-based platform that hosts Git repositories online, making it easier for developers to collaborate on projects. GitHub provides a graphical interface, tools for code review, issue tracking, and more. It’s essentially a place where Git repositories can be stored, managed, and shared.

---

### Where are Git and GitHub Used?

- **Git** is used locally on a developer's computer to manage and track changes in a project's files. It’s used in almost any software development environment, from small personal projects to large, collaborative enterprise projects.
- **GitHub** is used online to host and share Git repositories. It's commonly used for collaborative projects, open-source software development, and anywhere where multiple developers need to work together and manage their code in a centralized place.

---

### The Difference Between Git and GitHub

1. **Nature:**
   - **Git**: A version control system, a tool that helps you manage and track changes in your code.
   - **GitHub**: A hosting service for Git repositories, with additional features for collaboration, project management, and social coding.
2. **Functionality:**
   - **Git**: Works on your local machine, managing the history of your project.
   - **GitHub**: Provides a cloud-based platform to store and share your Git repositories, along with other tools for collaboration.
3. **Independence:**
   - **Git**: Can be used independently without GitHub.
   - **GitHub**: Requires Git to function, but is not necessary for using Git itself.
4. **Access:**
   - **Git**: Operates via a command-line interface, though GUI tools are available.
   - **GitHub**: Accessible through a web interface, with additional functionality available via GitHub Desktop or command-line integration.

In summary, Git is the version control tool that you use to manage your code, while GitHub is a platform that hosts your Git repositories online, making collaboration easier.

---

<h2 align="center">Git and Github commands</h2>
<p align="center">

| No. | Command                                | Description                                                                                                                       |
| --- | -------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| 1   | `git init`                             | This command initializes a new Git repository in the current directory.                                                           |
| 2   | `git status`                           | This command shows the current state of the working directory and the staging area.                                               |
| 3   | `stage`                                | This refers to the process of preparing a file for a commit.                                                                      |
| 4   | `git add "file name"`                  | This command adds a file to the staging area.                                                                                     |
| 5   | `git commit -m "message"`              | This command creates a new commit with the changes in the staging area, and the -m option allows you to provide a commit message. |
| 6   | `git log`                              | This command displays the commit history.                                                                                         |
| 7   | `git diff HEAD`                        | This command shows the changes between the working directory and the last commit.                                                 |
| 8   | `git diff --staged`                    | This command shows the changes between the staging area and the last commit.                                                      |
| 9   | `git reset "file name"`                | This command removes a file from the staging area.                                                                                |
| 10  | `git checkout -- "file name"`          | This command restores a file in the working directory to the state of the last commit.                                            |
| 11  | `git branch`                           | This command lists all the branches in the repository.                                                                            |
| 12  | `git branch "branch name"`             | This command creates a new branch with the specified name.                                                                        |
| 13  | `git checkout "branch name"`           | This command switches to the specified branch.                                                                                    |
| 14  | `git merge "branch name"`              | This command merges the specified branch into the current branch.                                                                 |
| 15  | `git rm "file name"`                   | This command removes a file from the repository.                                                                                  |
| 16  | `git branch -d "branch name"`          | This command deletes the specified branch.                                                                                        |
| 17  | `git clone "project address"`          | This command creates a local copy of a remote repository.                                                                         |
| 18  | `git push origin master`               | This command pushes the local commits to the remote repository's master branch.                                                   |
| 19  | `git pull origin master`               | This command fetches the latest changes from the remote repository's master branch and merges them into the local repository.     |
| 20  | `git remote`                           | This command manages the set of remote repositories.                                                                              |
| 21  | `git remote add origin "repo address"` | This command adds a new remote repository with the specified address.                                                             |

</p>

---
