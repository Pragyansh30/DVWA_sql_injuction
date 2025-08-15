# DVWA_sql_injuction
Objective

Demonstrate an SQL Injection vulnerability on a web application (DVWA) with Low Security.

Tools Used

DVWA (Damn Vulnerable Web Application)

Kali Linux

Firefox Browser


Steps Followed

1. Install and Configure DVWA

Cloned DVWA repository into /var/www/html/

Configured config.inc.php from config.inc.php.dist

Started Apache2 and MySQL services.


sudo cp /var/www/html/DVWA/config/config.inc.php.dist /var/www/html/DVWA/config/config.inc.php
sudo service apache2 start
sudo service mysql start


2. Access DVWA in Browser

Opened Firefox in Kali Linux.

Navigated to:

http://127.0.0.1/DVWA



3. Set Security Level to Low

Logged in with default DVWA credentials:

Username: admin
Password: password

Navigated to DVWA Security and selected Low.

Clicked Submit to save.



4. Perform SQL Injection

Went to SQL Injection section in DVWA.

In the input field, entered:

' OR '1'='1

Clicked Submit.

DVWA returned all user records, proving SQL Injection vulnerability.




Screenshots<img width="887" height="467" alt="Capture task3" src="https://github.com/user-attachments/assets/4d25b305-3819-4fff-a12d-aaf5dd3f06de" />


Terminal setup commands

DVWA Security set to Low

SQL Injection result


GitHub Deliverables

sql_injection_exploit.sh (placeholder script for demonstration)

Screenshots of setup, security setting, and injection result.
![tsk3](https://github.com/user-attachments/assets/a32fa4d5-8a0a-4e07-a29e-d1d94c65173d)

This README.md explaining the attack.


Example sql_injection_exploit.sh

#!/bin/bash
# Placeholder script for DVWA SQL Injection
echo "Accessing DVWA SQL Injection Page..."
firefox http://127.0.0.1/DVWA/vulnerabilities/sqli/

Vulnerability Explanation

SQL Injection occurs when user inputs are inserted directly into SQL queries without proper validation or sanitization.
By injecting ' OR '1'='1, we force the SQL query to always return true, bypassing authentication and revealing sensitive data.
