# Project 05: Secure Linux Server Permissions

## Objective
Configure Linux users, groups, file ownership, and permissions to protect shared project data from unauthorized access.

## Environment
- OS: Ubuntu 24.04 LTS (WSL2)
- Shell: Bash

## Implementation

### 1. Group and Users
Created the group 'projectteam'  and three users:
- alice: Authorized team member
- bob: Authorized team member
- charlie: Unauthorized user

Added Alice and Bob to 'projectteam'.

### 2. Shared Directory
Created '/srv/project-data'.

- Owner: root
- Group: Projectteam
- Permissions: 2770
- Setgid enabled to inherit the directory group.

### 3. Shared File
Created '/srv/project-data/shared.txt'.

- Owner: root
- Group: projectteam
- Permissions: 660

### 4. Access Control Tests

| User | Read | Write | Expected Result |
|---|---|---|---|
| Alice | Allowed | Allowed | Pass |
| Bob | Allowed | Allowed | Pass |
| Charlie | Denied | Denied | Pass |

## Results
Authorized team members successfully accessed and modified the shared file. The unauthorized user was denied both read and write access.

## Evidence
- 'screenshots/01-user-group-permissions.png'
- 'screenshots/02-access-control-tests.png'

## Conclusion
Linux group ownership, directory permissions, file permissions, and the setgid bit were used to implement and verify controlled access to shared project data.
