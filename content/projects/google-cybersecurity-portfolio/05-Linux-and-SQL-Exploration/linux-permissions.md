# Linux File Permissions Management
**Analyst:** Mohamed Aymen Chennoufi

### Scenario
As a security analyst, I was tasked with auditing the permissions of a sensitive directory to ensure that only authorized users in the `research` group had write access, while others had only read access.

### Commands & Actions
1. **Check current permissions:**
   `ls -l`
2. **Change ownership to the correct group:**
   `sudo chown :research sensitive_data.txt`
3. **Modify permissions (User: RW, Group: RW, Others: R):**
   `chmod 664 sensitive_data.txt`
4. **Verify changes:**
   `ls -l`

### Reflection
Properly managing `ugo` (User, Group, Other) permissions is the first line of defense against internal threats and lateral movement.
