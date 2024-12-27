# Web-Penetration-Testing-
Penetration testing exercise conducted on the OWASP Juice Shop. The objective was to identify and exploit common web vulnerabilities to understand their impact and remediation strategies.

Web Penetration Testing Report
Executive Summary
This report outlines the findings of a penetration testing exercise conducted on the OWASP Juice Shop. The objective was to identify and exploit common web vulnerabilities to understand their impact and remediation strategies. Key findings include successful exploitation of an admin path, brute-force password cracking, and a Cross-Site Scripting (XSS) vulnerability. These findings highlight the importance of robust security measures such as input validation, rate limiting, and secure authentication mechanisms.
Scope and Methodology
•	Scope: The scope of this assessment included the Juice Shop website, its APIs, and any accessible applications.
•	Approach: A black-box testing approach was adopted, simulating an external attacker with limited prior knowledge of the application.
•	Tools Used: 
o	Kali Linux
o	Burp Suite
o	Dirb
Vulnerability Findings
1.	Critical Vulnerability: Admin Path Discovery
o	Description: An admin panel was discovered through URL manipulation and directory brute-forcing techniques.
o	Risk: Unauthorized access to the admin panel grants attackers elevated privileges, allowing them to modify application data, manipulate user accounts, and potentially compromise the entire system.
o	Evidence:
 ![Screenshot_2024-12-27_04_09_17](https://github.com/user-attachments/assets/1224a925-d52d-4860-b470-f6ce8b33a1c3)
 
o	Remediation Steps: 
	Implement robust access control mechanisms, such as strong authentication and authorization rules.
	Minimize the exposed surface area by restricting access to sensitive areas and implementing appropriate URL obfuscation techniques.




2.	Critical Vulnerability: Admin Password Brute-Force
o	Description: The admin password was successfully cracked using the Hydra tool with a dictionary-based attack. The lack of rate limiting and account lockout mechanisms facilitated this attack.
o	Risk: Successful brute-force attacks compromise administrator accounts, granting attackers full control over the application and its data.
o	Evidence :
![Screenshot_2024-12-27_12_13_44](https://github.com/user-attachments/assets/a642d16d-f961-4aef-a65e-b59c7b50338b)

o	Remediation Steps: 
	Implement strong password policies, including minimum password length, complexity requirements, and the use of multi-factor authentication.
	Implement rate limiting to prevent automated attacks and account lockout mechanisms to deter brute-force attempts.




3.	Critical Vulnerability: Cross-Site Scripting (XSS) in Product Search
o	Description: An XSS vulnerability was identified in the product search functionality. Malicious scripts injected into the search field were reflected back to other users, allowing attackers to execute arbitrary JavaScript code in their browsers.
o	Risk: XSS vulnerabilities can be exploited to steal user credentials, hijack sessions, redirect users to malicious websites, or compromise the integrity of the application.
o	Evidence: <iframe src=”javascript:alert(‘successfully hacked’)”>
![Screenshot_2024-12-27_12_15_53](https://github.com/user-attachments/assets/5911d8ec-8072-42b4-bf25-9bdeb7912d11)
                                    
o	Remediation Steps: 
	Implement strict input validation and sanitization mechanisms to prevent the injection of malicious scripts.
	Encode or escape all user-supplied input before displaying it on the page.
	Employ a Content Security Policy (CSP) to further mitigate the impact of XSS attacks.


5.	Critical Vulnerability: SQL Injection in Product Search
o	Description: An SQL Injection vulnerability was found in the product search functionality. By carefully crafting the search query with malicious SQL commands, attackers can manipulate the database queries executed by the application. This could allow attackers to: 
	Read sensitive data: Access and retrieve confidential information from the database, such as user credentials, financial data, or internal documents.
	Modify data: Alter or delete existing data within the database, potentially disrupting application functionality or causing data loss.
o	Risk: SQL Injection vulnerabilities pose a severe threat, potentially leading to data breaches, system compromise, and severe service disruption.
o	Evidence:
![Screenshot_2024-12-27_12_24_02](https://github.com/user-attachments/assets/a12f8321-232c-487b-a641-e5105e10e899)

o	Remediation Steps: 
	Prepared statements: Use parameterized queries or prepared statements to prevent the direct inclusion of user input into SQL queries.
	Input validation and sanitization: Strictly validate and sanitize all user input before incorporating it into SQL queries. Escape or filter out any special characters that could be used to manipulate the query.
	Least privilege principle: Grant database users only the necessary permissions to perform their required tasks, minimizing the potential impact of a successful attack.

Exploitation and Attack Simulation
•	Tools and Techniques: 
o	Directory brute-forcing tools (Dirb) were used to discover hidden directories and files.
o	The burp suite tool was employed for password cracking.
o	Burp Suite was used for intercepting and manipulating HTTP requests, identifying vulnerabilities, and analyzing application behavior.
•	Outcome and Impact: 
o	Successful exploitation of the identified vulnerabilities demonstrated the potential for significant impact, including data breaches, system compromise, and reputational damage.
Conclusion
The penetration testing exercise revealed critical security vulnerabilities within the OWASP Juice Shop, highlighting the importance of proactive security measures. The findings underscore the need for robust security controls, including:
•	Secure authentication and authorization: Implement strong password policies, multi-factor authentication, and least privilege principles.
•	Input validation and sanitization: Validate and sanitize all user input to prevent injection attacks.
•	Regular security assessments: Conduct regular penetration tests and vulnerability scans to identify and address security weaknesses.
•	Security awareness training: Educate developers and users about security best practices and the importance of reporting suspicious activity.


