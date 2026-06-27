# Wazuh Brute Force Detection Lab

A detection engineering lab demonstrating how Wazuh can identify repeated authentication attempts in a controlled environment.

## Project Summary

This project documents a lab scenario where repeated login attempts were generated in a safe test environment and reviewed through Wazuh alerts. The goal was to understand how authentication activity appears in logs, how a SIEM detects suspicious patterns, and how alerts can support investigation.

## Skills Demonstrated

- Wazuh alert review
- Authentication log analysis
- Basic detection engineering workflow
- Network reconnaissance awareness
- Lab-safe event generation
- SIEM dashboard investigation
- Security documentation

## Lab Workflow

```text
Test activity generated
        ↓
Endpoint logs collected
        ↓
Wazuh agent forwards events
        ↓
Wazuh manager applies rules
        ↓
Alert appears in dashboard
        ↓
Analyst reviews evidence
```

## Tools Used

| Tool | Purpose |
|---|---|
| Wazuh | SIEM alerting and log analysis |
| Linux test host | Controlled lab target |
| Nmap | Lab network discovery and validation |
| Authentication logs | Evidence source |
| Wazuh dashboard | Alert review |

## Walkthrough

### 1. Network Discovery

Initial lab network visibility was checked before reviewing authentication activity.

<img src="https://i.imgur.com/Zz0dFOd.png" alt="Nmap commands">

### 2. Network Scan

A scan was used to identify hosts and services within the controlled lab network.

<img src="https://i.imgur.com/GVpW1QH.png" alt="Nmap scan">

### 3. Log Collection

Events were collected and reviewed to confirm that activity was visible to the SIEM.

<img src="https://i.imgur.com/1xAcJmq.png" alt="Log collection">

<img width="1350" height="491" alt="Log evidence" src="https://github.com/user-attachments/assets/2e5d1488-81fa-4e16-9c76-e24acd50b6ad" />

### 4. Detection Event

Repeated authentication activity was generated in the controlled lab and reviewed in Wazuh.

<img width="718" height="514" alt="Lab event" src="https://github.com/user-attachments/assets/cb8a8101-cb16-4c56-a897-024729afae6b" />

### 5. Wazuh Rule Triggered

The relevant Wazuh alert was triggered and reviewed from the dashboard.

<img width="1208" height="537" alt="Wazuh rule triggered" src="https://github.com/user-attachments/assets/5bbd57cf-fcd7-4435-a62b-ed9342198578" />

## Analyst Notes

When reviewing this type of alert, useful questions include:

- Which account was targeted?
- Which source IP generated the activity?
- Was the activity isolated or repeated?
- Did any login succeed after failures?
- Is the source expected in this environment?

## Key Takeaways

- SIEM alerts are strongest when supported by clear log evidence.
- Repeated authentication failures can indicate user error, misconfiguration, or hostile activity.
- Analysts should review source, account, timing, and outcome before deciding severity.
- Screenshots and notes make a lab more valuable as portfolio evidence.

## Future Improvements

- Add sample alert fields such as source IP, username, rule ID, and timestamp.
- Map the detection to MITRE ATT&CK.
- Add a short incident response checklist.
- Add false-positive notes and tuning ideas.
