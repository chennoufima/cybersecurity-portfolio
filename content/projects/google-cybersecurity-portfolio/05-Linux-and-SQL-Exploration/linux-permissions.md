# Linux File Permissions Audit & Remediation
**Analyst:** Mohamed Aymen Chennoufi

## Project Description
The research team at my organization required an update to the file permissions within the `projects` directory. The existing permissions did not align with the organization's authorization policies. My task was to audit the directory, deconstruct the permission strings, and implement the "Principle of Least Privilege" by restricting unauthorized write and execute access.

## 1. Auditing File and Directory Details
To begin, I needed to identify the current state of the filesystem. I used the `ls -la` command to provide a detailed listing, including hidden files.

**Command:**
`ls -la`

![Screenshot showing the projects directory listing](./images/linux_ls_la.png)

**Analysis of Output:**
The output revealed a directory named `drafts`, a hidden file `.project_x.txt`, and five standard project files. I identified the 10-character permission strings for each to determine where remediation was required.



## 2. Deconstructing the Permission String
Understanding the 10-character string is vital for accurate security administration. I analyzed the string for `project_t.txt` (`-rw-rw-r--`):

| Character Position | Representation | Actual Value | Meaning |
| :--- | :--- | :--- | :--- |
| 1st | File Type | `-` | Regular File |
| 2nd - 4th | User (Owner) | `rw-` | Read & Write access |
| 5th - 7th | Group | `rw-` | Read & Write access |
| 8th - 10th | Other | `r--` | Read-only access |

## 3. Changing File Permissions
The organization mandated that "Other" users should not have write access to any files. I identified that `project_k.txt` required an update to remove this risk.

**Action:** Removed write access for 'other' using the symbolic `chmod` method.
```bash
chmod o-w project_k.txt
ls -la
