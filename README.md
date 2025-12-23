# git-branching
This documentation contains the concepts of Learn Git Branching.
# Learn Git Branching
Git branching is a powerful feature of Git that allows developers to create multiple independent lines of development within a single repository. A branch is a lightweight pointer to a specific commit, not a copy of the entire project, which makes branching fast and efficient. The default branch, usually called main, contains the stable version of the project, while additional branches are created to work on new features, bug fixes, or experiments without affecting the main codebase. Developers can switch between branches, make commits independently, and later merge their changes back into the main branch. This approach helps in organizing work, improving collaboration among team members, and maintaining a clean and stable project history.
# Level-1 [Introduction Sequence ]
# 1.Introduction to Git Commits
What is Git Commit?

A Git commit is a snapshot of the project that records changes made to tracked files along with a unique identifier and message.
<img width="1911" height="874" alt="image" src="https://github.com/user-attachments/assets/25292dde-1716-4ae2-8d35-0ded823283c3" />
# Commands Executed
```bash
git commit
```
```
git commit
```
This screenshot shows how commits are created in Git.

Each circle (C0, C1, C2, C3) represents a commit made one after another.

The (main*) label shows the current branch, and it points to the latest commit (C3).

Every time git commit is used, a new commit is added and the main branch moves forward.

This helps us understand how Git keeps track of changes.


