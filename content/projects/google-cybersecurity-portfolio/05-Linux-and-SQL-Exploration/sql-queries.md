# Apply Filters to SQL Queries: Security Log Investigation
**Analyst:** Mohamed Aymen Chennoufi

## Project Description
In this project, I used Structured Query Language (SQL) to retrieve and filter data from an organization's database containing employee information and login attempt logs. My objective was to identify potential security threats, such as unauthorized after-hours access and suspicious login locations, while ensuring data privacy by filtering for specific departments.

---

## 1. Retrieve After-Hours Failed Login Attempts
To investigate potential brute-force attacks or unauthorized access attempts occurring outside of business hours, I filtered for failed logins (represented by `0`) that occurred after 18:00.

**SQL Query:**
```sql
SELECT * FROM log_in_attempts 
WHERE login_time > '18:00:00' AND success = 0;

**2. Retrieve Login Attempts on Specific Dates**
I was tasked with investigating a known security incident that occurred on a specific weekend. I filtered the logs to show all activity on '2022-05-09' and '2022-05-10'.

SQL Query:
SELECT * FROM log_in_attempts 
WHERE login_date = '2022-05-09' OR login_date = '2022-05-10';

**3. Retrieve Login Attempts Outside of Mexico**
To monitor for international travel or potential account hijacking from foreign IP addresses, I filtered for all login attempts that did not originate from Mexico.

SQL Query:
SELECT * FROM log_in_attempts 
WHERE NOT country LIKE 'MEX%';

**4. Retrieve Employees in Marketing**
For a permission audit, I retrieved a list of all employees within the Marketing department to verify their access levels in corporate tools like Jira and Confluence.

SQL Query:
SELECT * FROM employees 
WHERE department = 'Marketing';

**5. Retrieve Employees in Finance or Sales**
To ensure a mandatory Multi-Factor Authentication (MFA) rollout reached high-risk departments, I retrieved a list of all staff in Finance and Sales.

SQL Query:
SELECT * FROM employees 
WHERE department = 'Finance' OR department = 'Sales';

**6. Retrieve All Employees NOT in IT**
To audit general access permissions and ensure the Principle of Least Privilege, I filtered for every employee who does not belong to the IT department.

SQL Query:
SELECT * FROM employees 
WHERE NOT department = 'IT';

**Summary**
By applying SQL filters such as WHERE, AND, OR, and NOT, I extracted targeted security data to support incident response and identity management. I successfully identified failed logins at high-risk times, monitored geographic anomalies, and audited departmental access. This project demonstrates my ability to use data-driven insights to maintain a secure organizational posture.
