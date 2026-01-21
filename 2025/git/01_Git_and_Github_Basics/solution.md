# Week 4: Git and GitHub Challenge

## Challenge Tasks

## Task 1: Fork and Clone the Repository

1.Forked the "90daysofdevops" to my github account and renamed it as "My-90-days-of-devops".

2.Clone Your Fork Locally:

- Cloned the "My-90-days-of-devops" to the local repository(github_repos)

- Changed directory into the cloned repository:

   <img width="1888" height="262" alt="Screenshot 2026-01-19 221353" src="https://github.com/user-attachments/assets/5eace673-db30-40c6-9da5-2eb12c4edc26" />

## Task 2: Initialize a Local Repository and Create a File

### 1. Set Up Your Challenge Directory:

- using "mkdir week-4-challenge" command created a new directory "week-4-challenge" inside the cloned repository. 

### 2. Initialize a Git Repository:

- using "git init" command Initialized empty git repository inside week-4-challenge directory.

### Create a File:

- Using "vim info.txt" command created info.txt file and added intruductory content in it.

### Stage and Commit Your File:

- using "git add " command added info.txt to the staging area.

- using "git commit -m" command committed the info.txt file.

  <img width="2826" height="1416" alt="Screenshot 2026-01-19 233421" src="https://github.com/user-attachments/assets/eb33de77-6c5b-4e07-8535-67e1dde95fe3" />


## Task 3: Configure Remote URL with PAT and Push/Pull

### 1. Steps to Configure Remote URL with Your PAT:

- using "git remote -v" command in the local repository i checked it is connected to any remote repository,it is blank which means it is not connected to any remote repository.

- Copied my Remote github repository's HTTP URL which i want to connect and pasted it in the terminal as given below

```bash
# Replace <your-PAT> with actual values
git remote add origin https://guruprasad-97:<my-PAT>@github.com/guruprasad-97/shell-scripts.git
git remote set-url origin https://guruprasad-97:<my-PAT>@github.com/guruprasad-97/shell-scripts.git
git push -u origin main
```

## Task 4: Explore Your Commit History

   **check commit history**:

   ```bash
   git log
   ```

   Example output:

   <img width="2181" height="257" alt="Screenshot 2026-01-21 082250" src="https://github.com/user-attachments/assets/5079bb1c-a66e-4df7-a543-53b138539a99" />


## Task 5: Advanced Branching and Switching

  1. ### Create a New Branch:

     - created a New Branch called **"feature-update"** using the following command

       ```bash
       git branch feature-update
       ```
  2. ### Switch to the New Branch:

     - we can Use the following command to switch to the new branch

       ```bash
       git switch feature-update
       ```
     - Alternate command

       ```bash
       git checkout feature-update
       ```

       **Output**

       <img width="2305" height="260" alt="Screenshot 2026-01-21 090724" src="https://github.com/user-attachments/assets/7a0b0b4b-3b20-4260-89f5-43756dadf2f7" />

   3. ### Modify the File and Commit Changes:

      - Edited **info.txt**, added to the staging area and committed Using the following commands.

        ```bash
        echo "Adding more details to the file." >> info.txt
        git add info.txt
        git commit -m "Feature update: Added more content into info.txt"
        git push origin feature-update
        ```

        **Output**:

         <img width="2314" height="671" alt="Screenshot 2026-01-21 092725" src="https://github.com/user-attachments/assets/72c69dee-f5d7-467e-b816-e2e2a42e8d38" />

         <img width="2301" height="630" alt="Screenshot 2026-01-21 094529" src="https://github.com/user-attachments/assets/a6c3ef70-0930-4db7-97a8-5507ff334a4c" />


        

       
       












