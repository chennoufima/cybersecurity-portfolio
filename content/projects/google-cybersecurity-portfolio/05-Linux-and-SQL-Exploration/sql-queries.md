# SQL Security Query Investigation

### Objective
To identify potential brute-force attacks by filtering login logs for failed attempts from specific IP addresses.

### Query 1: Failed Login Attempts
```sql
SELECT * FROM log_in_attempts 
WHERE success = 0 
AND login_time > '2025-01-01';

### Query 2: Filtering by Specific Subnet
SELECT username, login_time, ip_address 
FROM log_in_attempts 
WHERE ip_address LIKE '192.168.1.%' 
AND success = 0;

