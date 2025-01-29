# Git: **Using Git for Team Collaboration and Tracking Changes in Projects**
>[!IMPORTANT]
> this part made by Davidokt


---

## What is Git Used For?

 **Version Control** – Keep a record of file modifications over time.
 **Collaboration** – Enable multiple programmers to contribute to the same project at once.
 **Branching and Merging** – Work on different features or bug fixes independently and integrate them into the main project later.
 **Backup and Restore** – Preserve the entire project history, making it possible to roll back to earlier versions if necessary.
 **Code Review** – Support reviewing code changes using pull requests (PRs) or merge requests (MRs).

---

## Key Git Actions and Commands

### 1. **Initialize a Repository**
   - Create a new Git repository:
     ```bash
     git init
     ```

### 2. **Clone a Repository**
   - Clone an existing repository:
     ```bash
     git clone <repository_url>
     ```

### 3. **Stage Changes**
   - Add files to the staging area:
     ```bash
     git add <file_name>
     ```
   - Add all changes:
     ```bash
     git add 
     ```

### 4. **Commit Changes**
   - Commit staged changes with a message:
     ```bash
     git commit -m "Your commit message"
     ```

### 5. **Check Status**
   - View the status of your working directory:
     ```bash
     git status
     ```

### 6. **View Commit History**
   - View the commit history:
     ```bash
     git log
     ```

### 7. **Branching**
   - Create a new branch:
     ```bash
     git branch <branch_name>
     ```
   - Switch to a branch:
     ```bash
     git checkout <branch_name>
     ```
   - Create and switch to a new branch:
     ```bash
     git checkout -b <branch_name>
     ```

### 8. **Merging**
   - Merge a branch into the current branch:
     ```bash
     git merge <branch_name>
     ```

### 9. **Pull Updates**
   - Fetch and merge changes from a remote repository:
     ```bash
     git pull
     ```

### 10. **Push Changes**
   - Push local changes to a remote repository:
     ```bash
     git push
     ```

### 11. **Revert Changes**
   - Undo changes in a file:
     ```bash
     git checkout -- <file_name>
     ```
   - Revert a commit:
     ```bash
     git revert <commit_hash>
     ```

### 12. **Stashing**
   - Temporarily save changes without committing:
     ```bash
     git stash
     ```
   - Apply stashed changes:
     ```bash
     git stash apply
     ```

### 13. **Tagging**
   - Create a tag for a specific commit (e.g., for releases):
     ```bash
     git tag <tag_name>
     ```

### 14. **Remote Management**
   - Add a remote repository:
     ```bash
     git remote add <remote_name> <repository_url>
     ```
   - View remote repositories:
     ```bash
     git remote -v
     ```

---
