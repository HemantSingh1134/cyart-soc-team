CYART SOC TEAM - WEEK 4 PROJECT
Threat Hunting and Incident Response using Wazuh SIEM

--------------------------------------------------
PROJECT OVERVIEW
--------------------------------------------------
This project demonstrates a complete Security Operations Center (SOC) workflow using Wazuh SIEM. It includes threat detection, analysis, and response based on a simulated SSH brute-force attack.

The project covers both theoretical concepts and practical implementation, including threat hunting, SOAR playbook design, alert triage, evidence analysis, adversary emulation, and post-incident analysis.

--------------------------------------------------
OBJECTIVE
--------------------------------------------------
- Perform threat hunting using Wazuh SIEM
- Detect suspicious login activities
- Simulate a brute-force attack
- Analyze logs and identify threats
- Design SOAR playbook for response
- Evaluate SOC performance using metrics

--------------------------------------------------
TOOLS USED
--------------------------------------------------
- Wazuh SIEM
- Kibana Dashboard
- Linux (SSH)
- Terminal

--------------------------------------------------
ATTACK SIMULATION
--------------------------------------------------
A brute-force attack was simulated using the following command:

ssh fakeuser@localhost

Multiple incorrect passwords were entered to generate failed login attempts.

--------------------------------------------------
THREAT HUNTING
--------------------------------------------------
Query used:
rule.id:5710

Findings:
- Multiple failed login attempts
- Invalid users (fakeuser, wronguser)
- Source IP (::1)
- Repeated attempts (firedtimes increase)

MITRE ATT&CK Mapping:
- T1110.001 (Password Guessing)
- T1021.004 (SSH)

--------------------------------------------------
SOAR PLAYBOOK
--------------------------------------------------
Workflow:
1. Detect Alert
2. Extract IP
3. Validate Attempts
4. Classify Attack
5. Block IP (simulated)
6. Create Ticket
7. Notify Admin

--------------------------------------------------
ALERT TRIAGE
--------------------------------------------------
Alert: SSH Failed Login Attempt
Rule ID: 5710
User: fakeuser
Priority: High

Reason:
- Multiple failed attempts
- Brute-force pattern

--------------------------------------------------
EVIDENCE ANALYSIS
--------------------------------------------------
Source: /var/log/auth.log

Evidence:
- Failed login attempts
- Invalid users
- Repeated activity

Conclusion:
Brute-force attack confirmed.

--------------------------------------------------
ADVERSARY EMULATION
--------------------------------------------------
Attack simulated using SSH login attempts.

Technique:
T1110 – Brute Force

Result:
Wazuh detected and logged the attack.

--------------------------------------------------
POST INCIDENT ANALYSIS
--------------------------------------------------
Root Cause:
Weak authentication controls

Recommendations:
- Account lockout policy
- Strong passwords
- Continuous monitoring

--------------------------------------------------
METRICS
--------------------------------------------------
MTTD: 1 hour
MTTR: 2 hours

--------------------------------------------------
CAPSTONE PROJECT
--------------------------------------------------
Complete SOC workflow implemented:
1. Attack simulation
2. Detection
3. Triage
4. Analysis
5. Response
6. Reporting

--------------------------------------------------
SCREENSHOTS
--------------------------------------------------
Figure 1: Wazuh Discover logs (Threat Hunting)
Figure 2: Log details (Evidence)
Figure 3: Repeated login attempts (Brute-force proof)
Figure 4: SSH attack simulation (Terminal)

--------------------------------------------------
CONCLUSION
--------------------------------------------------
This project successfully demonstrates SOC operations including detection, analysis, and response to a brute-force attack using Wazuh SIEM. The workflow improves security monitoring and incident response capabilities.

--------------------------------------------------
AUTHOR
--------------------------------------------------
Name: Hemant Chauhan
