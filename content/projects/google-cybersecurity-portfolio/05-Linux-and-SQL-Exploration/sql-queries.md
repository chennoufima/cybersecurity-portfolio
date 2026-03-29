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

### 2. Login Attempts on Specific Incident Dates
During a security incident investigation, I retrieved all login activity that occurred on **'2022-05-09'** and **'2022-05-10'** to track movement during a suspected breach.

```sql
SELECT * FROM log_in_attempts 
WHERE login_date = '2022-05-09' 
   OR login_date = '2022-05-10';
### 3. Logins Outside of Mexico
To monitor for potential account hijacking from foreign IP addresses, I filtered for any login attempts originating outside of Mexico using the `NOT` operator.

```sql
SELECT * FROM log_in_attempts 
WHERE NOT country LIKE 'MEX%';

### 4. Marketing Department Audit
I retrieved a list of all employees in the Marketing department to verify their access permissions for sensitive project folders. This audit ensures that only relevant personnel have access to specific marketing assets.

```sql
SELECT * FROM employees 
WHERE department = 'Marketing';

### 5. Finance and Sales MFA Rollout
To prepare for a mandatory Multi-Factor Authentication (MFA) update, I generated a list of all staff in the Finance and Sales departments. Targeting these departments was a priority due to the sensitive financial data they handle and the high risk associated with potential unauthorized access to fiscal records.

```sql
SELECT * FROM employees 
WHERE department = 'Finance' 
   OR department = 'Sales';

### 6. General Access Audit (Non-IT Staff)
I filtered for all employees who are **NOT** in the IT department. This audit is crucial for maintaining a secure environment by ensuring that administrative-level system access is restricted to the appropriate technical teams, strictly following the **Principle of Least Privilege (PoLP)**.

```sql
SELECT * FROM employees 
WHERE NOT department = 'IT';

---

## 📌 Summary
Through this project, I demonstrated how SQL is an essential tool for a security analyst to maintain organizational integrity. By utilizing filters such as `WHERE`, `AND`, `OR`, and `NOT`, I successfully isolated critical security events and audited departmental access permissions.

This hands-on exercise proved my ability to use data-driven insights to:
* **Identify Anomalies:** Spotting failed login attempts occurring after standard business hours.
* **Geofencing:** Detecting and isolating login attempts from unauthorized or high-risk countries.
* **Access Control:** Regularly auditing department lists to ensure system permissions in **Jira** and **Confluence** align perfectly with current job roles.

These queries directly support **Identity and Access Management (IAM)** and **Incident Response** workflows, showcasing a proactive approach to identifying vulnerabilities before they are exploited.
