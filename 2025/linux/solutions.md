# Week 2: Linux System Administration & Automation Challenge Solutions

## Task-1 user & group management

- Created the user "devops_user" and group "devops_team".
  <img width="635" height="177" alt="Screenshot 2026-01-08 094934" src="https://github.com/user-attachments/assets/2fc67c41-8435-4f8f-9068-3fbcc6a6d5ef" />


- created password and granted sudo access to the devops_user.
  <img width="1201" height="91" alt="Screenshot 2026-01-08 095256" src="https://github.com/user-attachments/assets/ab5cab88-d8e1-477a-bdc2-87d0f4364426" />


- Allowed ssh login for certain users("devops_user" & "guruprasad") in /etc/ssh/sshd_config.

## Task-2 File & Directory Permissions

- created the directory "devops_workspace" and a file "project_notes.txt".
- set permissions Owner can edit, group can read, others have no access for both.
- Verified permissions using ls -l
  <img width="1416" height="91" alt="Screenshot 2026-01-08 222556" src="https://github.com/user-attachments/assets/e4032373-36a0-4161-866a-dba851d9d507" />

## Task-3 Log File Analysis with AWK, Grep & Sed




