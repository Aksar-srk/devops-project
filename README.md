# DevOps swiggy-clone Project – Git Branching & Workflow

This project demonstrates Git best practices for a DevOps workflow using **branching**, **feature branches**, **pull requests**, and **merges**.  
We used a Swiggy-like project setup to practice.

---

## 🔹 Branching Strategy

- **main** → Stable production-ready branch  
- **dev** → Development/integration branch  
- **feature-\*** → Feature-specific branches  

Example:
- `feature-docker`
- `feature-swiggy-setup`

---

## 🔹 Step 1: Initialize Git Repository

```bash
git init
git remote add origin https://github.com/<username>/devops-project.git
git branch -M main
git push -u origin main
```

## 🔹 Step 2: Create Development Branch
```bash
git checkout -b dev
git push -u origin dev
```
## 🔹 Step 3: Create Feature Branches
```bash
# Docker feature
git checkout -b feature-docker
git push -u origin feature-docker

# Swiggy setup feature
git checkout -b feature-swiggy-setup
git push -u origin feature-swiggy-setup
```
## 🔹 Step 4: Add Files & Commit Changes
```bash
git add .
git commit -m "Added Swiggy project setup files"
git push origin feature-swiggy-setup
```
🔹 Errors Faced & Fixes
warning: in the working copy of 'Dockerfile', LF will be replaced by CRLF...
✅ Fix:
```bash
git config --global core.autocrlf false
git rm --cached -r .
git reset --hard
```
🔹 to know current branch
```bash
git branch
```
## 🔹 Step 5: Pull Request Workflow

- Push feature branch to GitHub
- Open Pull Request (PR) from feature-* → dev
- Team reviews code
- If approved → Click Merge Pull Request

## 🔹 Step 6: Merge Feature → Dev
```bash
# On GitHub via PR
feature-swiggy-setup → dev
```

## 🔹 Step 7: Merge Dev → Main (Production)
Once testing in dev is complete:

# On GitHub via PR
- dev → main
- This makes the project stable and production-ready.
- # Merge workflow (via GitHub PR)
- feature-branch → dev → main
- ✅ Final Workflow Diagram
```css
 feature-docker ─────┐
 feature-swiggy-setup ──┐
                       │
                       ▼
                     [ dev ]
                       │
                       ▼
                     [ main ]
```
                     

### Notes
- Always create new features in feature-* branches.
- Merge to dev after review.
- Merge dev → main only after testing.
- .gitignore is used to avoid unnecessary files.
- Tags can be used for versioning:
```bash
git tag v1.0
git push origin v1.0
```







