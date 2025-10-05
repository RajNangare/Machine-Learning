# Git Cheat Sheet & Workflow

---

## 1️⃣ Basic Git Commands

| Command | Purpose | Notes / Examples |
|---------|---------|-----------------|
| git init | Initialize a Git repository in a folder | Use in your project folder to start tracking it with Git |
| git status | Check the status of your repo | Shows staged, unstaged, and untracked files |
| git add <file> / git add . | Stage changes for commit | git add . stages all files; git add filename stages specific file |
| git commit -m "message" | Save staged changes as a snapshot | Write descriptive commit messages, e.g., "Added data preprocessing script" |
| git remote add origin <repo-url> | Link local repo to GitHub | Example: git remote add origin git@github.com:username/repo.git |
| git branch -M main | Rename current branch | Makes your branch name consistent with GitHub standards |
| git push -u origin main / git push origin main | Push local commits to GitHub | -u sets upstream for future pushes |
| git push --force | Force push to overwrite remote branch | Use only if remote is empty or you want to replace it |
| git pull origin main | Pull changes from GitHub | Use --allow-unrelated-histories if merging local repo with an independent remote |
| git log | View commit history | Shows all commits in the branch |
| git reset --soft HEAD~1 | Undo last commit but keep changes staged | Useful for fixing mistakes |
| git reset <file> | Unstage a file | Removes file from staging area without deleting changes |
| git clone <repo-url> | Copy remote repo to local machine | git clone git@github.com:username/repo.git; git clone <repo-url> MyFolder to rename folder locally |

---

## 2️⃣ Typical Workflow

1. Work locally: edit or add files in your project folder.
2. Check changes:
   git status
3. Stage changes:
   git add .
4. Commit changes:
   git commit -m "Describe changes"
5. Pull updates from GitHub:
   git pull origin main
6. Push changes to GitHub:
   git push origin main

> After initial setup, git pull ensures you’re synced and avoids conflicts.

---

## 3️⃣ Force Push (For Empty Remote)

If your GitHub repo is empty (just a README.md) and you want to push your local project:

git push -u origin main --force

> Replaces remote content with your local files. Safe if remote has nothing important.

---

## 4️⃣ Tips for Clean Git Workflow

- Pull before starting work to avoid conflicts.
- Commit frequently with meaningful messages.
- Use --force only when the remote is empty or you intend to overwrite it.
- Organize your projects in folders: ~/Projects/ProjectName
- Keep branch names consistent (main is standard)
- Stage only files you want to commit (git add <file>) for more control.

---

## 5️⃣ Recommended Folder Structure

~/Projects/
    ├─ ML-Projects/
    │    ├─ Project1/
    │    │    ├─ src/
    │    │    ├─ data/
    │    │    └─ README.md
    │    └─ Project2/
    ├─ Web-Projects/
    │    ├─ Site1/
    │    └─ Site2/

> Each project gets its own Git repository for better organization and version control.

---

## ✅ Summary

- Local ↔ Remote sync: git pull → make changes → git add → git commit → git push
- Use SSH for secure, password-free pushes.
- Force push only for empty or new repos.
- Keep commits small, meaningful, and frequent for best practices.
