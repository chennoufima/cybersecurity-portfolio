# SQL Security Query Investigation

### Objective
To identify potential brute-force attacks by filtering login logs for failed attempts from specific IP addresses.

### Query 1: Failed Login Attempts
```sql
SELECT * FROM log_in_attempts 
WHERE success = 0 
AND login_time > '2025-01-01';


