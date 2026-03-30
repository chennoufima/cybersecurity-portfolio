# Python Automation: Updating Access Control Lists (ACL)
**Analyst:** Mohamed Aymen Chennoufi

---

## 📝 Project Description
In this project, I developed a Python script to automate the management of an "allow list" for restricted network assets. The goal was to create an efficient, repeatable process for removing unauthorized IP addresses from a security file, ensuring that the organization's access controls remain up-to-date without manual intervention.

---

## ⚙️ The Automation Logic
The script follows a structured algorithm to manage the `allow_list.txt` file:
1. **Open the file** containing the current allow list.
2. **Read the content** and convert it into a string.
3. **Convert the string into a list** for easier manipulation.
4. **Iterate through the remove list** to identify IPs that no longer belong.
5. **Update the list** by removing those IPs.
6. **Overwrite the original file** with the updated, secure list.

---

## 🐍 The Python Script
```python
# Assign the file name to a variable
import_file = "allow_list.txt"

# List of IP addresses that should no longer have access
remove_list = ["192.168.97.225", "192.168.158.170", "192.168.201.40", "192.168.58.92"]

# Open the file and read its initial contents
with open(import_file, "r") as file:
    ip_addresses = file.read()

# Convert the string of IPs into a list
ip_addresses = ip_addresses.split()

# Iterate through the remove_list to update the allow list
for element in remove_list:
    if element in ip_addresses:
        ip_addresses.remove(element)

# Convert the list back into a string with new lines
ip_addresses = "\n".join(ip_addresses)

# Overwrite the file with the updated IP list
with open(import_file, "w") as file:
    file.write(ip_addresses)

print("Access Control List updated successfully.")
