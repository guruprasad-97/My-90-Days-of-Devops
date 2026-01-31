# Git & GitHub Advanced Challenge - Solution

This document contains the solutions and explanations for the **Week 4: Git & GitHub Advanced Challenge**.

---

## **Task 1: Working with Pull Requests (PRs)**

### **Steps to Create a Pull Request**

1. **Fork and Clone a Repository**

   ```bash
   git clone <https://github.com/guruprasad-97/ultimate-linux-guide.git>
   cd ultimate-linux-guide/
   ```

2. **Create a Feature Branch and Make Changes**

   ```bash
   git checkout -b feature-branch
   echo "New Feature" >> feature.txt
   git add .
   git commit -m "Added a New Feature"
   ```
   **Hands on Practice**:

   <img width="1753" height="326" alt="Screenshot 2026-01-30 082034" src="https://github.com/user-attachments/assets/05be9a03-8457-4bce-b01d-65a36bb31eec" />

3. **Push the Changes and Create a Pull Request**

   ```bash
   git push origin feature-branch
   ```

   **Hands on Practice**:

   <img width="1736" height="553" alt="Screenshot 2026-01-30 083408" src="https://github.com/user-attachments/assets/a2bd9e23-711f-499b-bf0e-5d661e12a5c3" />

4. **Open a PR on GitHub, Request Review, and Merge After Approval**

   **Hands on Practice**:

   <img width="2751" height="1099" alt="Screenshot 2026-01-30 083916" src="https://github.com/user-attachments/assets/7da11fb4-3154-4456-90bf-1de629c6841d" />

   <img width="2616" height="1170" alt="Screenshot 2026-01-30 084025" src="https://github.com/user-attachments/assets/fff502e5-11fe-4b86-b2bc-7baeec5b1d24" />

   <img width="2583" height="1329" alt="Screenshot 2026-01-30 084148" src="https://github.com/user-attachments/assets/3ae5e757-ec4d-479c-9b18-ed86b6f29192" />

   <img width="2686" height="1145" alt="Screenshot 2026-01-30 084228" src="https://github.com/user-attachments/assets/1c973439-f4cf-4edc-8ab0-ee492102e728" />

   <img width="2642" height="1100" alt="Screenshot 2026-01-30 084313" src="https://github.com/user-attachments/assets/578f9a2d-c5b7-4a84-a990-6a16bebfa188" />

---

## **Task 2: Undoing Changes – Reset & Revert**

### **Example Scenario**

1. **Create and Commit a File**

   ```bash
   echo "wrong code" >> wrong.txt
   git add .
   git commit -m "committed by mistake"
   ```

2. **Soft Reset (Keeps Changes Staged)**

   ```bash
   git reset --soft HEAD~1
   ```

3. **Mixed Reset (Unstages Changes but Keeps Files)**

   ```bash
   git reset --mixed HEAD~1
   ```

4. **Hard Reset (Removes All Changes)**

   ```bash
   git reset --hard HEAD~1
   ```

5. **Revert a Commit Safely**

   ```bash
   git revert HEAD
   ```
   **Hands on Practice**:

   <img width="2031" height="885" alt="Screenshot 2026-01-30 101028" src="https://github.com/user-attachments/assets/d51fee5b-2e71-4d0f-928e-a6eb92cd1065" />

   <img width="1570" height="1189" alt="Screenshot 2026-01-30 101051" src="https://github.com/user-attachments/assets/244b5773-07ca-4589-8856-daae9e430c63" />

### **Differences Between `reset` and `revert`**

| Feature  | `git reset` | `git revert` |
|----------|------------|--------------|
| Removes commit? | Yes (for `--hard`) | No |
| Preserves history? | No | Yes |
| Best for public branches? | No | Yes |

**When to Use Each Method:**

- Use `reset` when working on local commits before pushing.
- Use `revert` when undoing changes in a shared branch.

---

## **Task 3: Stashing - Save Work Without Committing**

### **Example Scenario**

1. **Modify a File Without Committing**

   ```bash
   echo "Temporary Changes" >> temp.txt
   git add .
   ```

2. **Stash the Changes**

   ```bash
   git stash
   ```

3. **Switch to Another Branch and Apply the Stash**

   ```bash
   git checkout main
   git stash pop
   ```

**Hands on Practice**:

<img width="1761" height="875" alt="Screenshot 2026-01-31 094819" src="https://github.com/user-attachments/assets/953df822-f433-4c7e-a9f7-a45c6f40f454" />

### **When to use `git stash`**

You use `git stash` when you want to temporarily save your uncommitted changes (both staged and unstaged) without committing them, so you can work on something else and come back later.

### **Differences Between `git stash pop` and `git stash apply`**

- `git stash pop`: Applies the stashed changes and removes them from the stash list.
- `git stash apply`: Applies the stashed changes but keeps them in the stash list.

---

## **Task 4: Cherry-Picking - Selectively Apply Commits**

### **Example Scenario**

1. **Find the Commit to Cherry-Pick**

   ```bash
   git log --oneline
   ```

2. **Apply a Specific Commit to the Current Branch**

   ```bash
   git checkout main
   git cherry-pick <commit-hash>
   ```

**Hands on Practice**:

<img width="2182" height="1368" alt="Screenshot 2026-01-31 175818" src="https://github.com/user-attachments/assets/98f410ad-b71a-4b95-bce0-dc309bd35f2e" />

### **How Cherry-Picking is Used in Bug Fixes**

- Quickly apply critical fixes to different branches without merging unwanted changes.
- Useful in release/hotfix workflows.

### **Risks of Cherry-Picking**

- Can create duplicate commits if not used carefully.
- May cause merge conflicts if the code has changed significantly.

---

## **Task 5: Rebasing - Keeping a Clean Commit History**

### **Example Scenario**

1. **Fetch the Latest Changes**

   ```bash
   git fetch origin main
   ```

2. **Rebase the Feature Branch onto Main**

   ```bash
   git rebase origin/main
   ```

3. **Resolve Conflicts and Continue**

   if conflicts occur,resolve it by

   - Open conflicted files
   - Fix conflicts manually
   - Remove conflict markers

   ```bash
   git add <filename>
   git rebase --continue
   ```

**Hands on Practice**:

<img width="1674" height="1016" alt="Screenshot 2026-01-31 205139" src="https://github.com/user-attachments/assets/322747bc-80c1-445d-bd0c-703ee0ed36a8" />

   
### **Difference Between `merge` and `rebase`**

| Feature | `git merge` | `git rebase` |
|---------|------------|--------------|
| Creates extra merge commits? | Yes | No |
| Preserves history? | Yes | No |
| Recommended for feature branches? | No | Yes |

### **Best Practices for Rebasing**

- Use interactive rebase (`git rebase -i`) to clean up commits.
- Avoid rebasing shared branches to prevent conflicts.
- Always test after rebasing to ensure functionality.

---

## **Task 6: Branching Strategies Used in Companies**

### **Common Git Workflows**

1. **Git Flow**: Git Flow is a strict, role-based branching model designed for release-driven projects.

   **Core Branches(Always Exist)**

   - **main(or master)**:
     - Production ready code
     - Every commit here = release
     - Tagged with versions (v1.0, v1.1)

   - **develop**:
     - Integration branch
     - contains latest completed features
     - source branch for all new work.

   **Supporting branches(temporary)**

   **feature/***:Purpose of this branch is to create new features
    - created from `develop`
    - merged back into `develop`
    - Naming: feature/login,feature/payment

    **workflow**:

      ```bash
      develop → feature/* → develop
      ```

   **release/***:the purpose of this branch is to prepare a production release

    - created from `develop`
    - merged into `develop` and `main`
    - used for bug fixes,docs,version dump

    **workflow**:

      ```bash
      develop → release/* → main + develop
      ```

   **hotfix/***: Purpose of this branch is emergency production fixes

    - created from `main`
    - merged into `main` and `develop`
    - used when prod is broken

    **workflow**:

      ```bash
      main → hotfix/* → main + develop
      ```


2. **GitHub Flow**: GitHub Flow is a lightweight, continuous-delivery–friendly branching strategy.

   **Branches Structure**

   `main`:

   - Always deployable
   - Reflects production-ready code
   - Protected branch (no direct commits)

   `feature/*`:

    - Created from `main`
    - used for features,bug fixes,experiments
    - Deleted after merge


3. **Trunk-Based Development**:In this all developers commit their code changes directly to a single shared branch (the “trunk” or “main”), keeping changes small, frequent, and continuously integrated.

   **Branch Structure**

   **main**:

    - Single source of truth
    - Always deployable
    - Protected with CI checks,code reviews

    **Short-lived branches**(optional)

    - Created from `main`
    - Live for a few hours or 1 day
    - Merged back immediately

---

### **Example of Simulating a Git Workflow**

```bash
git branch feature-1
git branch hotfix-1
git checkout feature-1
```

### **Which Strategy is Best for DevOps and CI/CD?**

- **Trunk-Based Development** is preferred for DevOps due to its fast iteration cycle.
- **GitHub Flow** works well for teams practicing continuous delivery.
- **Git Flow** is useful for teams with planned release cycles.

---

## **Final Submission Steps**

1. **Pushing the Work to GitHub**

   ```bash
   git add .
   git commit -m "Completed Git & GitHub Advanced Challenge"
   git push origin main
   ```

2. **Create a Pull Request** with a detailed description.


---

## **Conclusion**

This challenge covered essential Git concepts that are crucial for DevOps workflows. Mastering these topics will help in real-world version control, collaboration, and CI/CD practices.

   

   

   
     

   

   






  






   







   
   
   
