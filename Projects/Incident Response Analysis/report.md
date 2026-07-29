# Incident Response Report

## Summary
A fictional multimedia company experienced a Denial of Service (DoS) attack that disrupted internal network services. Using the NIST Cybersecurity Framework (CSF), I analysed the incident and gave recommendations on how the likelihood future incidents can be reduced.

## Incident Overview
### Attack type
DoS (Denial of Service)
### Attack method
ICMP Flood
### Attack impact
- Internal network unavailable
- Business disruption
- Critical services temporarily affected
- Non-critical services taken offline during recovery

## NIST CSF Analysis
### Identify
My investigation revealed that the company was attacked through an unconfigured firewall. This allowed the malicious actor(s) to flood the network with ICMP packets. This meant that authorised internal network traffic couldn't access network resources, causing the network to stop responding.  

### Protect
The network security team implemented the following to prevent future attacks:
- New firewall rule limiting the rate of incoming ICMP packets
- IDS system to filter out ICMP traffic based on suspicious characteristics

### Detect
The network security team set up network monitoring software to detect abnormal traffic patterns as well as configured the firewall to check for spoofed IP addresses on the incoming ICMP packets. 

### Respond
For future events the team will:
- Isolate affected parts of the network to prevent further disruption
- Attempt to restore critical networks to ensure business continuity
- Analyse network logs for suspicious activity
- Report to the company's management team and, if required the appropiate authorities.

### Recover
To recover from the ICMP flood attack, the team will:
- Restore network services to a normal functioning state.
- Bring non-critical network services offline to reduce network traffic internally, restoring critical services first
- Restore non-critical services once malicious ICMP traffic has been blocked
 
### Reflection
This project has helped me improve my understanding of incident response and how to apply the NIST Cybersecurity framework.

It has also showed me the signifiance one error (i.e. a firewall misconfiguration) can have to an organisation.
  

