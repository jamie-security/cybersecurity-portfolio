# Google Cybersecurity Professional Certificate: Notes
**Progress:** Courses 5/9 completed
**Provider:** Google/Coursera

These are the key takeaways and my personal notes from the certificate. My notes will be updated as I progress through each course.


# Course 1: Foundations of Cybersecurity
## Key Concepts
### Cybersecurity
Is the practice of ensuring confidentiality, integrity, and availability of information by protecting networks, devices, people & data from unauthorised access/criminal exploitation.

### CIA Triad
A foundational model that helps inform how organisations consider risk.
- **Confidentiality:** Only authorised users can access specific assets/data
- **Integrity:** Data is correct, authentic,and reliable.
- **Availability:** Data is accessible to those authorised to access it.

### Security Controls
Safeguards designed to reduce security risk. Can be technical, physical or administrative.
Examples include:
- Firewalls
- Access controls
- Security policies
- Locks
- CCTV

### Cybersecurity Frameworks & Regulations
Course 1 introduced me to common frameworks used by organisations as well as key regulations that organisations should follow.

Examples include:
- NIST CSF
- GDPR
- PCI DSS

### Key Takeaways From Course 1
- Cybersecurity protects the confidentiality, integrity and availability of information.
- Organisations use multiple types of security controls to reduce risk.
- These controls are not only technical, but also physical and administrative.

---
# Course 2: Play It Safe: Manage Security Risks
## Key Concepts
### Threats
Any potential event that can negatively impact an organisations assets. 
### Risk
Anything that can impact the confidentiality, integrity and availability of an organisations assets.
### Vulnerabilities
Weaknesses that can be exploited by a threat.
Examples:
- Weak passwords
- Misconfigured systems
- Unpatched software

### Risk Management
Risk management is the process where an organisations security professionals identify potential threats and vulnerabilities, assess their impact to the organisation, and implement the appropiate security controls.

NIST have developed a framework for risk management which include 7 categories: Prepare, categorise, select, implement, assess, authorise and monitor.

### Principle of Least Privilege
Users should only have the minimum access necessary to perform their tasks. This limits the potential damage if their credentials are compromised.

### Project
I applied the concepts of course 2 when completing a security audit project. In this project I reviewed the security controls of a fictional organisation and identified missing controls as well as recommended improvements.

 [Course 2 security audit project](../../Projects/Security%20Audit/README.md)

### Key Takeaways From Course 2
- Organisations perform risk management to identify and prioritise risk
- Vulnerabilities can lead to organisations being exposed more to threats
- The principle of least privilege reduces unnecessary access to systems and data

---
# Course 3: Connect and Protect: Networks and Network Security
## Key Concepts
### Network
A group of connected devices that communicate with each other. Types of networks include LANs and WANs.

Some examples of network tools include hubs, switches, routers and modems.

### Cloud networks
A collection of servers/computers that store resources and data in remote data centres that can be accessed via the internet. 

CSPs provide 3 main services: Software as a service, Infrastructure as a service and Platform as a service. 

Cloud networks can provide reliability, decreased costs and increased scalability for organisations. 

### TCP/IP Model
Framework used to visualise how data is organised and transmitted across networks. Helps network engineers conceptualise processes on the network and communicate where disruptions or security threats occur.

The TCP/IP model has 4 layers: Network access layer, internet layer, transport layer and application layer.

### Network Security
Involves protecting networks and network resources from unauthorised access, attacks, and disruptions.

### Firewalls
Monitors traffic to and from a network. Types of firewalls include hardware, software and cloud-based firewalls. 

Firewalls that are misconfigured or not configured at all create security vulnerabilities.

### Denial of Service
DoS attacks target networks or servers and flood them with network traffic. 

There are different types of DoS attacks including DDoS, SYN flood attack, ICMP flood and ping of death. 

In the project as part of course 3, ICMP flooding was used as a DoS attack. 

### Project
In this project I completed an incident response analysis on a fictional company which had experienced an ICMP flood attack.

To analyse the incident, I used the five parts of the NIST Cybersecurity Framework:
1. Identify
2. Protect
3. Detect
4. Respond
5. Recover

[Course 3 incident response project](../../Projects/Incident%20Response%20Analysis/README.md)

## Key Takeaways from Course 3
- Cloud networking can help organisations reduce costs whilst having a reliable network provided to them by a CSP
- Firewalls, if misconfigured, create security vulnerabilities which can lead to DoS attacks.
- Incident response gives organisations a structured approach to dealing with security incidents

---
# Course 4: Tools of the Trade: Linux and SQL
## Linux

### Linux Command Line
I developed practical experience using the Linux command line to navigate directories and manage file permissions.

Commands used during the course include:
```
cd
ls
ls -la
chmod
```
### File Permissions
File permissions in Linux determine what users can do with files and directories.

There are 3 ownership categories in Linux for setting permissions, they are:
- User: An individual owning the file/directory
- Group: A collection of users who share common access to files/directories
- Other: All other users on the system who aren't owners or part of a group

Permissions are then split up into 3 main types:
- Read (r)
- Write (w)
- Execute (x)

Permissions in Linux are represented in a 10-character string, example:
```
-rwxrw-r--
```
The first character in the string represent the file type. In my example, the file type is a regular file. The remaining 9 characters represent the user, group and other.

### chmod
To modify permissions in Linux, the ```chmod``` command is used. 

Example:
```chmod g-x drafts```
My example above removes execute permissions from the group for the drafts directory.

### Hidden Files
To display hidden files in linux, the comand ```ls -la``` is used. 

To know if a file is hidden or not, a ```.``` will be at the beginning of the file name.

### Project
I completed a project reviewing and modifying Linux file permissions within a fictional organisation.

[Course 4 Linux project](../../Projects/File%20Permissions:%20Linux/README.md)

## SQL
### SQl Queries
SQL is used to retrieve and filter information stored in databases.

I practiced using:
- ```SELECT```
- ```FROM```
- ```WHERE```
- ```AND```
- ```OR```
- ```NOT```
- ```LIKE```

```SELECT``` and ```FROM``` are used to retrieve all the information in a database. ```WHERE``` is used to filter the information from the database For example:
```
SELECT *
FROM log_in_attempts
WHERE login_time > '18:00';
```
In my example, everything is selected from the log_in_attempts table, but only the results where login_time is after 18:00 are displayed.

### AND
```AND``` is used with ```WHERE``` and it requires that both conditions are true.
Example:
```
SELECT *
FROM log_in_attempts
WHERE login_time > '18:00` AND success = 0;
```
This example will identify failed login attempts that occured after 18:00. 

### OR
```OR``` is also used with ```WHERE```. It allows either condition to be true.
Example:
```
SELECT *
FROM employees
WHERE department = 'Finance' OR department = 'Sales';
```
This example will identify employees in either the finance or sales departments.

### NOT
```NOT``` is used to exclude records matching a condition
Example:
```
SELECT *
FROM employees
WHERE NOT department = 'Information Technology';
```
This example will identify employees that are in any other department that isn't IT.

### LIKE & Wildcards
```LIKE``` is used to search for patterns rather than exact values. 
The ```%``` wildcard represents zero or more characters.
Example:
```
SELECT *
FROM employees
WHERE department = 'Marketing' AND office LIKE 'East%';
```
This exmaple will identify employees in the marketing department with offices beginning with ```East```.

### Project
I used SQL to investigate a security issue involving login attempts and employee information.
I investigated:
- Failed login attempts after business hours
- Login attempts on specific dates
- Login attempts originating outside Mexico
- Marketing employees in the East building
- Finance and Sales employees
- Employees outside the IT department

[Course 4 SQL project](../../Projects/Security%20Investigation:%20SQL/README.md)

## Key Takeaways from Course 4
- Linux provides useful tools for security administration & access control
- File permissions are an important part of implementing least privilege
- SQL can be used to investigate and filter security-related data
- ```AND```, ```OR```, and ```NOT``` are used to create targeted queries
- ```LIKE``` and ```%``` are used to identify patterns.

---
# Course 5: Assets, Threats and Vulnerabilities
## Key Concepts


