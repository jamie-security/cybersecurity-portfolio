# REPORT

## Summary

The following report is part of my project reviewing the security posture of Botium Toys, a fictional organisation. To complete the review, I analysed a security audit report created by Botium Toys.

My analysis has allowed me to identify strengths, as well as weaknesses of Botium Toys security posture, increasing their exposure to security risks.

This project was part of the Google Cybersecurity Professional Certificate course.

## Existing Security Controls

The audit conducted by Botium Toys revealed that the following security controls had been implemented:
- Firewall
- Antivirus software
- Physical controls (Locks and CCTV)
- Fire detection and prevention systems

These controls provide Botium Toys with a baseline level of protection against security threats, lacking controls to prevent or detect advanced security threats.

## Missing Security Controls

The audit revealed the lack of important security controls, which should be prioritised:
- Least privilege
- Disaster recovery plan
- Password policies
- Separation of duties
- Intrusion Detection System
- Backups
- Monitoring and maintenance of legacy systems
- Encryption
- Password management system

Not having these controls in place will put Botium Toys at risk of unauthorised access (internal & external), data loss and disruption to services. 

## Compliance

### PCI DSS

Botium Toys showed some compliance with PCI DSS requirements, however, several improvements need to be made. Including:
- Secure storage of credit card information
- Data encryption
- Password management

These compliance gaps put payment information at an increased risk of being compromised.

### GDPR

Similarly to PCI DSS, Botium Toys showed some compliance with the EU's GDPR. However, some improvements still need to be made to be fully compliant, including:
- E.U. customers' data being kept private and secured
- Data classification and inventory

Ensuring full compliance with GDPR will keep E.U. customer data safe as well as preventing sanctions.

## Recommendations
Based on my findings above, I have recommended the following to Botium Toys:
- Apply the principle of least privilege
- Develop and maintaining a disaster recovery plan to prevent the loss of data, as well as to ensure business continuity.
- Introduce strong password policies alongside a centralised password management system. This will prevent unauthorised access to systems and data from external threats through the use of employee accounts.
- Deploy an intrusion detection system to provide continuous monitoring of networks to help detect advanced threats that may bypass existing firewalls. 
- Clear methods when handling legacy systems i.e. a maintenance schedule as well as ensuring intervention methods are clear
- Encryption of sensitive data 

By implementing my recommendations, Botium Toys will improve their security posture, as well as comply with industry standards and regulations.

## Reflection
This project has allowed me to improve my understanding of how organisations assess their security posture and how they prioritise improvements based on risks identified. The project has also helped me understand the importance of combining different types of security controls (technical, administrative and physical) to reduce risk.
