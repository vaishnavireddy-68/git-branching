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

What is Git Rebase?

Git rebase is a Git operation used to integrate changes from one branch into another by moving or replaying commits on top of a new base commit. Instead of creating a merge commit like Git merge, rebase rewrites the commit history so that the branch appears as if it was created from the latest commit of the target branch. This results in a cleaner, linear project history that is easier to read and understand. During a rebase, Git temporarily removes the commits from the current branch, updates the branch to the latest version of the target branch, and then reapplies the removed commits one by one. Git rebase is commonly used for local branches to keep the commit history tidy, but it should be avoided on shared or public branches because it rewrites history.
<img width="1904" height="875" alt="image" src="https://github.com/user-attachments/assets/90630d69-0294-4ae5-9908-0d9d88fddd7d" />
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
git checkout bugfix
```
```
git rebase main
```
This screenshot shows how rebasing works in Git using two branches.

The circles (C0, C1, C2, C3) represent commits created at different times on different branches.

The main branch has its own commits, and the bugFix* label shows the branch where the bug fix work is done.

First, commits are made separately on the main and bugFix branches.

When the command git rebase main is used on the bugFix branch, Git takes the bug fix commit and places it on top of the latest commit of the main branch.

After rebasing, both branches contain the same changes, and the commit history becomes clean and straight.

This helps us understand how Git can organize commits neatly while keeping all changes.

The commit history begins linearly from C0 to C1, after which it splits into two branches.

The main branch points to commit C3, while the bugfix* branch is currently checked out and points to C2, as indicated by the * symbol showing that HEAD is on the bugfix branch.

The diagram shows that the bugfix commit has been moved and reapplied on top of the latest commit of the main branch, resulting in a straight, linear history.
The renaming of the commit to C2′ visually represents that the commit was recreated during the rebase process.
# Level -2 [Ramping Up]
# 1.Detach yo' HEAD
Detach yo’ HEAD in Git refers to a situation called the detached HEAD state, where the HEAD pointer is no longer attached to a branch but instead points directly to a specific commit. Normally, HEAD points to the latest commit of a branch, but when you check out a particular commit, tag, or past version, Git detaches HEAD from the branch. In this state, you can view, test, or even make changes and create new commits, but those commits are not associated with any branch and may be lost if you switch to another branch without saving them. To preserve work done in a detached HEAD state, you must create a new branch. This state is mainly used for exploring project history, debugging older versions, or testing previous commits without affecting the main branch.

<img width="1909" height="875" alt="image" src="https://github.com/user-attachments/assets/9c7c619b-e30e-461f-9da4-fa6783e28823" />
# Command Executed
```bash
git checkout C4
```
This screenshot shows what happens when HEAD is detached in Git.

The commits (C0, C1, C2, C3, C4) show the history of the project.

At first, HEAD is normally connected to a branch like main or bugFix.

When the command git checkout C4 is used, Git moves HEAD directly to commit C4.

Now, HEAD is not pointing to any branch, it is pointing only to that commit.

The branches (main and bugFix) stay where they were and do not move.

This state is called detached HEAD.

It helps us understand how Git can look at any old commit without changing branch history.
# 2.Relative Refs (^)
Relative refs (^) in Git are a way to refer to commits relative to another commit, usually the current HEAD. The caret symbol (^) means “the parent commit” of a given commit. For example, HEAD^ refers to the commit immediately before the current one, and HEAD^^ refers to the grandparent commit (two commits before). Relative refs are especially useful for navigating commit history, checking out previous states of the project, or performing operations like reset, checkout, or rebase without needing to know exact commit hashes. They make working with Git history easier and more readable by allowing developers to move backward through commits using simple notation.

<img width="1905" height="866" alt="image" src="https://github.com/user-attachments/assets/49142016-5ecf-4559-9792-367705c90abf" />

# Commands Executed
```bash
git checkout bugFix
```
```
git checkout C3
```
n these screenshot Git checkout bugFix moves you to the bugFix branch.

Git checkout C3 moves HEAD to commit C3, not to a branch, so this is called detached HEAD.

The ^ symbol means go to the previous commit.
# 3.Relative Refs #2 (~)
Relative refs () in Git are used to refer to a commit that is a certain number of steps before another commit, usually starting from HEAD. The tilde symbol () followed by a number indicates how many commits to go back in a straight line. For example, HEAD1 refers to the immediate previous commit, HEAD2 refers to two commits before, and HEAD~3 refers to three commits before the current commit. Relative refs using ~ are especially useful for quickly navigating commit history and performing Git operations like checkout, reset, or rebase without needing to remember long commit hashes.
<img width="1913" height="879" alt="image" src="https://github.com/user-attachments/assets/656c868b-8e1a-49cc-848d-3284f526902a" />

# Commands Executed
```bash
git checkout C1
```
```
git branch -f bugFix C0
```
```
git branch -f main C6
```
These screenshot shows Git checkout C1 moves you directly to commit C1.

Git branch -f bugFix C0 forces the bugFix branch to point to commit C0.

Git branch -f main C6 forces the main branch to point to commit C6.

# 4.Reversing Changes in Git
Reversing changes in Git refers to the process of undoing or rolling back modifications made to files or commits in a repository. Git provides several commands to reverse changes depending on the situation—for example, discarding uncommitted changes, undoing a commit, or reverting a specific commit from history. Commands like git checkout or git restore can be used to discard changes in the working directory, while git reset is used to move the current branch pointer to a previous commit, optionally keeping or removing changes. For already shared commits, git revert is preferred because it safely creates a new commit that reverses the effects of an earlier one without rewriting history. Overall, reversing changes in Git allows developers to correct mistakes, experiment freely, and maintain a clean and reliable project history.

<img width="1918" height="870" alt="image" src="https://github.com/user-attachments/assets/ae1e3c60-9b4f-40e2-ae5a-cb11d9be1a08" />
# Commands Executed
```bash
git checkout local
```
```
git reset --hard C1
```
```
git checkout pushed
```
```
git revert pushed
```
Git checkout local moves you to the local branch.

Git reset --hard C1 moves the branch back to commit C1 and removes later changes.

Git checkout pushed switches you to the pushed branch.

Git revert pushed creates a new commit that undoes the changes made in the pushed commit.










