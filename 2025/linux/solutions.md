# Week 2: Linux System Administration & Automation Challenge Solutions

## Task-1 user & group management

- **Created the user "devops_user" and group "devops_team"**

  <img width="635" height="177" alt="Screenshot 2026-01-08 094934" src="https://github.com/user-attachments/assets/2fc67c41-8435-4f8f-9068-3fbcc6a6d5ef" />


- **created password and granted sudo access to the devops_user**

  <img width="1201" height="91" alt="Screenshot 2026-01-08 095256" src="https://github.com/user-attachments/assets/ab5cab88-d8e1-477a-bdc2-87d0f4364426" />


- Allowed ssh login for certain users("devops_user" & "guruprasad") in /etc/ssh/sshd_config.

## Task-2 File & Directory Permissions

- created the directory "devops_workspace" and a file "project_notes.txt".
- set permissions Owner can edit, group can read, others have no access for both.
- Verified permissions using ls -l

  <img width="1416" height="91" alt="Screenshot 2026-01-08 222556" src="https://github.com/user-attachments/assets/e4032373-36a0-4161-866a-dba851d9d507" />

## Task-3 Log File Analysis with AWK, Grep & Sed

- **used "grep" to find all the occurences of "authentication Failure" and printed only first 10 lines**

  <img width="2304" height="887" alt="Screenshot 2026-01-09 100523" src="https://github.com/user-attachments/assets/1dafa152-4fb4-49b0-9beb-828a76b69c64" />

- **using "awk" extracted timestamps and loglevels**

  <img width="1611" height="650" alt="Screenshot 2026-01-09 205901" src="https://github.com/user-attachments/assets/5d156a89-07fb-4f94-afdd-8abef34e115a" />

- **Using "sed" replaced all IP addresses with [REDACTED] for security**
  <img width="1867" height="719" alt="Screenshot 2026-01-09 213113" src="https://github.com/user-attachments/assets/71a9d1e4-53db-43ae-9a35-966c248cff57" />

- **Found the most frequent log entry using sort | uniq -c | sort -nr | head -10**
  <img width="1900" height="453" alt="Screenshot 2026-01-09 220805" src="https://github.com/user-attachments/assets/8fbbd0de-62bf-4c21-bcf0-5c5a1c3160bd" />






