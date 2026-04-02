This README is designed to serve as a quick-reference "cheat sheet" for your personal workflow, covering everything from initial repository setup to handling common version control mishaps.

---

# 🚀 Git & GitHub Reference Guide

A personal collection of essential Git commands and workflows for managing repositories, handling conflicts, and fixing mistakes.

## 📂 Repository Setup & Migration

### Initializing a New GitHub Page
To set up a personal portfolio or site using the `academicpages` template:

1.  **Create on GitHub:** Go to [github.com/new](https://github.com/new) and name it `pyaelinn01.github.io`.
2.  **Local Configuration:**
    ```bash
    # Rename existing template remote to 'upstream'
    git remote rename origin upstream

    # Ensure local branch is named 'main'
    git branch -M main

    # Link to your new personal repository
    git remote add origin https://github.com/pyaelinn01/pyaelinn01.github.io.git

    # Push and set tracking
    git push -u origin main
    ```

### Initializing a New Project
```bash
# Set global identity
git config --global user.name "Your Name"
git config --global user.email "you@example.com"

cd /path/to/your/project
git init

# Add remote (SSH or HTTPS)
git remote add origin git@github.com:username/mlopsTuto.git

# Rename branch and push
git branch -M main
git push -u origin main
```

---

## 🔄 Syncing & Updating

### Pulling with Different Histories
If you are merging two repositories that were started independently:
```bash
git pull origin main --allow-unrelated-histories
```

### Cloning Specific Branches
To clone only a single branch without the entire history of the repository:
```bash
git clone --branch "branch-name" --single-branch "repository-url"
```

---

## 🛠 Fixing Mistakes & Conflicts

### Undoing the Last Commit
If you committed something by mistake but want to **keep the changes** in your code:
```bash
git reset --soft HEAD~1
```

### Resolving Conflicts (The "Rebase" Way)
When changes exist on `main` that conflict with your local work:
```bash
git pull origin main
git rebase
```

### The "Nuclear" Option (Hard Reset)
To completely discard local changes and match the remote repository exactly:
```bash
git fetch origin
git reset --hard origin/main
```

---

## 💡 Quick Tips
* **Check Status:** Always run `git status` before pushing.
* **Origin vs. Upstream:** `origin` is your fork/personal repo; `upstream` is usually the original source you pulled from.
* **Branch Management:** Use `git branch -M main` to ensure you aren't using the older `master` naming convention.
