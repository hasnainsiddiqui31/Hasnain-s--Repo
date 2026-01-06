# 📘 Standard Operating Procedure (SOP)
## 🌳 Git Branching Strategy

<p align="center">
  <img src="docs/images/git-branching.png" width="90%" alt="Git Branching Strategy">
</p>

---

## 📄 Document Information

| Attribute | Details |
|---------|--------|
| Document Title | SOP – Git Branching Strategy |
| Version | 1.0 |
| Author | Hasnain Siddiqui |
| Created On | January 2026 |
| Last Updated | January 2026 |
| Audience | Developers, DevOps, Release Managers |

---

## 🎯 Purpose

This SOP defines a **standard Git branching strategy** to:

- Keep the codebase clean and structured
- Enable parallel development
- Reduce merge conflicts
- Ensure stable and controlled releases
- Improve team collaboration

---

## 📌 Scope

Applicable to:
- All repositories
- Development, staging, and production environments
- Teams using CI/CD pipelines

---

## 🌳 Branching Strategy

### 🔹 Main Branches

**`main`**
- Production-ready code
- Always stable
- Protected branch

**`develop`**
- Integration branch
- Base for all features

---

### 🌿 Supporting Branches

**Feature Branch**

**Bugfix Branch**

**Release Branch**

**Hotfix Branch**

---

## 🔄 Workflow

### 🧩 Feature Development Flow

1. Create a feature branch from `develop`
2. Implement the new feature
3. Commit changes frequently
4. Push the branch to remote
5. Create a Pull Request (PR) to `develop`
6. Review and merge after approval

```bash
git checkout develop
git pull origin develop
git checkout -b feature/<feature-name>
git add .
git commit -m "feat: <feature description>"
git push origin feature/<feature-name>
```

---


## 🐞 Bugfix Flow

1. Create a bugfix branch from `develop`
2. Fix the issue
3. Commit and push the changes
4. Create a Pull Request (PR) to `develop`
5. Merge after review and approval

```bash
git checkout develop
git pull origin develop
git checkout -b bugfix/<bug-description>
git add .
git commit -m "fix: <short bug description>"
git push origin bugfix/<bug-description>
```
---

### 🚀 Release Flow

1. Create a release branch from `develop`
2. Perform final testing and stabilization
3. Apply only bug fixes (no new features)
4. Update version and documentation
5. Merge the release branch into `main`
6. Tag the production release
7. Merge the release branch back into `develop`

``` bash
git checkout develop
git pull origin develop
git checkout -b release/<version>

git checkout main
git merge release/<version>
git tag v<version>
git push origin main --tags

git checkout develop
git merge release/<version>
git push origin develop
```

---

### 🔥 Hotfix Flow

1. Create a hotfix branch from `main`
2. Fix the critical production issue
3. Commit and test the fix
4. Merge hotfix into `main`
5. Tag the hotfix release
6. Merge hotfix back into `develop`

``` bash
git checkout main
git pull origin main
git checkout -b hotfix/<issue-name>

git add .
git commit -m "fix: <critical issue description>"

git checkout main
git merge hotfix/<issue-name>
git tag v<hotfix-version>
git push origin main --tags

git checkout develop
git merge hotfix/<issue-name>
git push origin develop
```
---

## ✅ PULL REQUEST RULES (COPY–PASTE)

markdown
### 🔐 Pull Request (PR) Rules

- Minimum **1 reviewer** required
- All CI/CD checks must pass
- Direct commits to `main` and `develop` are not allowed
- PR title and description must be clear
- Linked issue/ticket recommended

  
## 📝 Commit Message Format

Use the following standard format for all commits:

### Commit Types
- **feat** – New feature
- **fix** – Bug fix
- **docs** – Documentation changes
- **chore** – Maintenance tasks
- **refactor** – Code refactoring
- **test** – Test-related changes

### Examples
- `feat: add user authentication`
- `fix: resolve login issue`
- `docs: update branching SOP`
- `chore: update dependencies`

---

## ✅ Best Practices

- Keep branches short-lived  
- Sync frequently with `develop`  
- Write meaningful commit messages  
- Delete branches after merge  
- Tag every production release  
- Protect critical branches  

---

## 🧪 Versioning & Tagging

This project follows **Semantic Versioning**:

### Version Examples
- `v1.0.0` – Initial release  
- `v1.1.0` – New feature  
- `v1.1.1` – Bug fix  

### Tag a Release

```bash
git tag v1.0.0
git push origin v1.0.0
```

## 🛡️ Branch Protection Rules

- No direct pushes to `main` and `develop`  
- Pull request approval required before merging  
- All CI/CD checks must pass before merge  
- Automatically delete branches after merge  

---

## 📚 References

| Reference | Link |
|-----------|------|
| Git Documentation | https://git-scm.com/doc |
| GitHub Docs | https://docs.github.com |
| Semantic Versioning | https://semver.org |
---

## 🖼 Author Image

<p align="center">
  <img src="docs/images/hasnain.png" width="120" style="border-radius:50%" alt="Author Hasnain Siddiqui">
</p>


---

## ✍️ Author & Sign-off

**Author:** Hasnain Siddiqui  
**Role:** DevOps & Cloud Engineer  

**Signature:**  
Hasnain Siddiqui  

**Date:** January 2026

---

> 📌 This SOP must be followed for all repositories unless explicitly approved by the engineering lead.




