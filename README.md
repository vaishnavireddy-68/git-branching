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
 # 2.Introduction to Git Branching
 What is Git Branch?

A Git branch is a lightweight pointer to a commit that allows you to work on code independently without affecting the main branch.
<img width="1910" height="875" alt="image" src="https://github.com/user-attachments/assets/30fcc89e-c32c-435b-8e3b-da7b02200a88" />
# Commands Executed
```bash

git branch bugfix
```
```
git checkout bugfix
```
This screenshot shows how to create and switch to a new branch in Git using Learn Git Branching.

The commits C0 and C1 are displayed, with C1 being the latest commit.

A new branch named bugfix has been created from commit C1 using git branch bugfix, and it has been checked out using git checkout bugfix.

The * symbol next to bugfix indicates that HEAD is currently on this branch.

The main branch still points to commit C1, but the active branch is now bugfix.
# 3.Introduction to Git Merging
What is Git Merging?

When you work on different features using branches, Git merge helps you bring the work from one branch into another (usually into the main or master branch).
<img width="1906" height="862" alt="image" src="https://github.com/user-attachments/assets/3ef383f5-7b05-47b1-b153-ce33c0c96b2d" />
# Commands Executed
```bash
git branch bugfix
```
```
git checkout bugfix
```
```
git commit
```
```
git checkout main
```
```
git commit
```
```
git merge bugfix
```
This screenshot illustrates the Merging in Git level from Learn Git Branching, showing how Git manages multiple branches and combines them.

The circles labeled C0, C1, C2, C3, and C4 represent individual commits, with the history first moving linearly from C0 to C1 and then splitting into two paths.

From commit C1, a new branch named bugfix is created and points to commit C2, while the main branch continues independently with commits C3 and C4.

The label main* indicates that the main branch is currently checked out, with the * symbol showing that HEAD is pointing to main at commit C4.

The curved lines in the diagram visually represent the divergence of the two branches and their integration through a merge.
# 4.Introduction to Rebase






