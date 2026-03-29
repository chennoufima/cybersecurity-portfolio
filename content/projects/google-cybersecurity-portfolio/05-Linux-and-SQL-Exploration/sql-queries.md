# Apply Filters to SQL Queries: Security Log Investigation
**Analyst:** Mohamed Aymen Chennoufi

---

## 📝 Project Description
As a security analyst, I used Structured Query Language (SQL) to audit organization-wide login activity and employee data. My goal was to identify security anomalies, such as unauthorized after-hours access and logins from restricted geographic regions, while ensuring data privacy by filtering departmental access.

---

## 🔍 Security Investigations

### 1. After-Hours Failed Login Attempts
To identify potential brute-force attacks, I filtered for failed login attempts (`success = 0`) that occurred after 18:00.
```sql
SELECT * FROM log_in_attempts 
WHERE login_time > '18:00:00' 
  AND success = 0;
