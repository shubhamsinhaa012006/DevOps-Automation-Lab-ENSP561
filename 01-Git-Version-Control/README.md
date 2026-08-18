# Experiment 01: Git Version Control & Collaborative Development

## Objective

Set up a Git repository and practice branching, merging, and collaborative development. Create a small project and manage code versions using Git.

## Problem Statement

Understand how to use version control systems to track changes and collaborate efficiently. The goal of this experiment is to initialize a local Git repository, link it to GitHub, use a feature-branch workflow, and resolve any conflicts using standard Git commands.

---

## Prerequisites & Software Required

### Software Required
- **Git**
- **Visual Studio Code (VS Code)**
- **Python 3.x**

### Tools Used
- **Git Bash / Terminal**
- **GitHub**

---

## Directory Structure

```text
01-Git-Version-Control/
│
├── screenshots/          # Contains screenshots demonstrating successful execution
│   └── .gitkeep
├── dev.py                # Sample Python file used for demonstrating Git version control.
├── login.py              # Sample Python file used for demonstrating Git version control.
└── README.md             # Experiment documentation (You are here)
```

---

## Basic Theory

**Git** is a distributed version control system that tracks changes in any set of computer files, usually used for coordinating work among programmers. 

Key Concepts:
- **Repository:** A folder tracked by Git.
- **Commit:** A saved state of the repository.
- **Branch:** An independent line of development.
- **Merge:** Combining changes from different branches.
- **Pull Request (PR):** Proposing changes to be merged on GitHub.

---

## Commands Used

| Command | Description |
| :--- | :--- |
| `git init` | Initializes a new local Git repository. |
| `git clone <url>` | Copies a remote repository to your local machine. |
| `git status` | Shows the working tree status. |
| `git add <file>` | Stages files for a commit. |
| `git commit -m "<msg>"`| Records changes with a descriptive message. |
| `git branch <name>` | Creates a new branch. |
| `git checkout <name>` | Switches to the specified branch. |
| `git merge <name>` | Merges the specified branch into the current one. |
| `git push` | Uploads local changes to a remote repository. |
| `git pull` | Fetches and integrates changes from a remote repository. |

---

## Procedure

1. **Repository Initialization:**
   Open the terminal, navigate to the folder, and run `git init`.
2. **First Commit & Remote Push:**
   Stage files using `git add .`, commit them with `git commit`, link your GitHub repository using `git remote add`, and push using `git push`.
3. **Feature Branch Workflow:**
   Create a new branch with `git checkout -b <branch-name>`. Make changes to `login.py`, commit them, and push the branch to GitHub.
4. **Merging:**
   Open a Pull Request on GitHub, review the changes, and merge them into the main branch. Pull the updated main branch locally.

---

## Screenshots Section

Add screenshots of Git commands and GitHub workflow here after completing the experiment.

---

## Expected Output

- A local Git repository correctly linked to GitHub.
- Created branches and successful commits.
- A merged Pull Request on GitHub.

---

## Learning Outcome

By the end of this experiment, we learned how to initialize a repository, use essential Git commands, manage feature branches, and collaborate using GitHub Pull Requests.

---

## Conclusion

The fundamental concepts of Git and GitHub for version control and collaboration were successfully implemented. 

## References

- [Official Git Documentation](https://git-scm.com/doc)
- [GitHub Flow Guide](https://docs.github.com/en/get-started/quickstart/github-flow)
