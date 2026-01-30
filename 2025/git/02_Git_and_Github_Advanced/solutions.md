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




   







   
   
   
