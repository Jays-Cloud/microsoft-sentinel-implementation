# Microsoft Sentinel Implementation & Threat Hunting

**Type:** Lab Project — AZ-500 Studies  
**Skills:** SIEM Deployment, Log Analytics, Data Connectors, KQL Queries, Analytic Rules, SOAR Playbooks, Incident Response  

---

## Overview
As part of my AZ-500 studies, I implemented **Microsoft Sentinel** to collect, analyze, and respond to security events in an Azure environment.  
I followed the core steps from the official [Microsoft Learning Lab 11](https://github.com/MicrosoftLearning/AZ500-AzureSecurityTechnologies/blob/master/Instructions/Labs/LAB_11_Microsoft%20Sentinel.md), expanding on them with additional testing and customizations to deepen my understanding of SIEM operations, KQL-based threat detection, and automated response workflows.

---

## Objectives
- Onboard Microsoft Sentinel and integrate with a Log Analytics Workspace.  
- Connect the **Azure Activity** data connector to ingest subscription-level activity logs.  
- Create an **analytic rule** based on the Azure Activity connector.  
- Develop a **SOAR playbook** (Logic App) to automate incident response.  
- Link the playbook to the analytic rule for automated execution.  
- Generate a test incident and validate automated actions.  
- Investigate the incident using Sentinel’s built-in tools.  

---

## What I Did

### 1. Onboarded Microsoft Sentinel
- Created a dedicated **Log Analytics Workspace** in the Azure Portal.  
- Enabled Microsoft Sentinel on that workspace to serve as the SIEM platform.

### 2. Connected Data Sources
- Configured the **Azure Activity** data connector to capture subscription and resource-level events.  
- Validated ingestion by querying for recent activity logs.

### 3. Built an Analytic Rule
- Created a **scheduled query rule** leveraging the Azure Activity connector to identify key events.  
- Set the rule to trigger an incident when specific conditions were met.

### 4. Created a SOAR Playbook
- Designed a **Logic App** playbook to automate the response — sending alerts to an email address and posting a Teams notification when an incident was created.  
- Tested the playbook independently to ensure correct execution.

### 5. Linked the Playbook to the Analytic Rule
- Configured the analytic rule to automatically **run the playbook** upon detection of a matching event.

### 6. Generated & Investigated an Incident
- Triggered a test event to invoke the analytic rule and playbook.  
- Used the **Investigation Graph** to analyze event relationships, confirm playbook execution, and document findings.

---

## Key Takeaways
- **Playbooks (Logic Apps)** enable automated, repeatable response actions, reducing manual workload in the SOC.  
- Integrating **alerts with automated workflows** combines detection and response for faster mitigation.  
- The **Azure Activity connector** provides visibility into subscription-level changes critical for governance and security monitoring.  
- Hands-on use of **KQL queries** reinforces the importance of targeted log analysis for incident detection.  

---

## Next Steps
- Connect additional high-value data sources (e.g., Microsoft Defender for Endpoint, Azure AD sign-ins).  
- Develop custom hunting queries for common attack techniques like lateral movement or persistence.  
- Build additional playbooks for automated containment actions.  

---

## References
- [Microsoft Sentinel Documentation](https://learn.microsoft.com/azure/sentinel/)  
- [Official AZ-500 Lab 11: Microsoft Sentinel](https://github.com/MicrosoftLearning/AZ500-AzureSecurityTechnologies/blob/master/Instructions/Labs/LAB_11_Microsoft%20Sentinel.md)  
