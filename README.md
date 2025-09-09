
# Vulnerability Management Program Implementation Project

In this project, we simulate the implementation of a comprehensive vulnerability management program, from inception to completion.

_**Inception State:**_ the organization has no existing policy or vulnerability management practices in place.

_**Completion State:**_ a formal policy is enacted, stakeholder buy-in is secured, and a full cycle of organization-wide vulnerability remediation is successfully completed.

---

<img width="1000" alt="image" src="https://github.com/user-attachments/assets/cfc5dbcf-3fcb-4a71-9c13-2a49f8bab3e6">

# Technology Utilized
- Tenable (enterprise vulnerability management platform)
- Azure Virtual Machines (Nessus scan engine + scan targets)
- PowerShell & BASH (remediation scripts)

---


# Table of Contents

- [Vulnerability Management Policy Draft Creation](#vulnerability-management-policy-draft-creation)
- [Mock Meeting: Policy Buy-In (Stakeholders)](#step-2-mock-meeting-policy-buy-in-stakeholders)
- [Policy Finalization and Senior Leadership Sign-Off](#step-3-policy-finalization-and-senior-leadership-sign-off)
- [Mock Meeting: Initial Scan Permission (Server Team)](#step-4-mock-meeting-initial-scan-permission-server-team)
- [Initial Scan of Server Team Assets](#step-5-initial-scan-of-server-team-assets)
- [Vulnerability Assessment and Prioritization](#step-6-vulnerability-assessment-and-prioritization)
- [Distributing Remediations to Remediation Teams](#step-7-distributing-remediations-to-remediation-teams)
- [Mock Meeting: Post-Initial Discovery Scan (Server Team)](#step-8-mock-meeting-post-initial-discovery-scan-server-team)
- [Mock CAB Meeting: Implementing Remediations](#step-9-mock-cab-meeting-implementing-remediations)
- [Remediation Round 1: Outdated Wireshark Removal](#remediation-round-1-outdated-wireshark-removal)
- [Remediation Round 2: Insecure Protocols & Ciphers](#remediation-round-2-insecure-protocols--ciphers)
- [Remediation Round 3: Guest Account Group Membership](#remediation-round-3-guest-account-group-membership)
- [Remediation Round 4: Windows OS Updates](#remediation-round-4-windows-os-updates)
- [First Cycle Remediation Effort Summary](#first-cycle-remediation-effort-summary)

---

### Vulnerability Management Policy Draft Creation

This phase focuses on drafting a Vulnerability Management Policy as a starting point for stakeholder engagement. The initial draft outlines scope, responsibilities, and remediation timelines, and may be adjusted based on feedback from relevant departments to ensure practical implementation before final approval by upper management.  
[Draft Policy](https://docs.google.com/document/d/1GyModW2FDC5TQ93H9LioB2XPoqUv8Pf9ScA_BUj4al0/edit?tab=t.0)

---

### Step 2) Mock Meeting: Policy Buy-In (Stakeholders)

In this phase, a meeting with the server team introduces the draft Vulnerability Management Policy and assesses their capability to meet remediation timelines. Feedback leads to adjustments, like extending the critical remediation window from 48 hours to one week, ensuring collaborative implementation.

# Policy Discussion Meeting

**Participants:**  
- Jimmy  
- Victoria  

---

**Jimmy:** Good morning, Victoria. How have things been? I know the past few weeks have been quite busy.  

**Victoria:** Good morning, Jimmy. It has been a bit hectic, but we are managing. I reviewed the draft policy, and overall it looks solid. However, with our current staffing levels, it will be difficult to meet the proposed remediation timelines—particularly the 48-hour requirement for critical vulnerabilities.  

**Jimmy:** I understand. That timeline is quite aggressive, especially at the start. As a compromise, we could extend the critical vulnerability remediation window to one week. The 48-hour response could be reserved for truly urgent cases, such as zero-day vulnerabilities.  

**Victoria:** That adjustment would be very helpful. We would also appreciate some flexibility during the initial phase as our team adapts to the new remediation and patching process—perhaps for the first few months.  

**Jimmy:** That makes sense. Once the policy is finalized, the program will officially begin, but we are planning to provide all departments with a six-month adjustment period to become comfortable with the new process. Does that sound reasonable?  

**Victoria:** Yes, that sounds fair. Thank you for considering our input. It’s reassuring to be included in the decision-making process—it helps ensure we feel part of the overall solution.  

**Jimmy:** Absolutely. This is a collective effort, and we value everyone’s collaboration.  

**Victoria:** Thank you, Jimmy. I appreciate your time.  

**Jimmy:** Likewise. Thanks for keeping this discussion efficient.  

**Victoria:** Agreed. I’ll talk to you soon.  

---

### Step 3) Policy Finalization and Senior Leadership Sign-Off

After gathering feedback from the server team, the policy is revised, addressing aggressive remediation timelines. With final approval from upper management, the policy now guides the program, ensuring compliance and reference for pushback resolution.  

[Policy Production with Sign-off
](https://docs.google.com/document/d/1OCJwhK_w9VAcrmsjxZf8KfeaEs08xN2MA7VWFkUmBys/edit?tab=t.0)


---



### Step 4) Mock Meeting: Initial Scan Permission (Server Team)

The team collaborates with the server team to initiate scheduled credential scans. A compromise is reached to scan a single server first, monitoring resource impact, and using just-in-time Active Directory credentials for secure, controlled access.  

# Vulnerability Scanning Discussion

**Participants:**  
- Jimmy  
- Victoria  

---

**Victoria:** Good morning, Jimmy. I hear you’re preparing to begin some vulnerability scans.  

**Jimmy:** That’s correct. Now that our vulnerability management policy is in place, I’d like to start conducting scheduled credentialed scans across your environment.  

**Victoria:** Sounds good. What’s involved, and how can our team assist?  

**Jimmy:** We’re planning weekly scans of the server infrastructure. We estimate it will take about 4–6 hours to scan approximately 2,200 assets. To perform accurate assessments, we’ll need administrative credentials so the scan engine can remotely log into the targets.  

**Victoria:** I see. Before we proceed, could you clarify what scanning entails? I’m concerned about resource utilization, and I also want to ensure that granting credentials to all systems is handled securely.  

**Jimmy:** Those are valid concerns. The scan engine sends controlled traffic to the servers to identify vulnerabilities. This includes checking the registry, detecting outdated software, and identifying insecure protocols or cipher suites. Credentials are required to provide deeper visibility.  

**Victoria:** Understood. As long as the scans don’t disrupt server operations, we can proceed. I suggest starting with a single server to monitor performance and resource usage before expanding.  

**Jimmy:** That’s a good approach. Regarding credentials, could your team create a dedicated account in Active Directory? You can keep the account disabled until scanning begins, enable it during the scan, and then disable or deprovision it immediately afterward. This would provide just-in-time access and reduce risk.  

**Victoria:** That works for us. I’ll ask Susan to begin automating the provisioning and deprovisioning process for these accounts.  

**Jimmy:** Excellent. Once the credentials are ready, we’ll move forward with the first scan.  

**Victoria:** Perfect. I’ll keep you updated.  

**Jimmy:** Thank you, Victoria. Talk soon.  

**Victoria:** Talk soon.  




### Step 5) Initial Scan of Server Team Assets

In this phase, an insecure Windows Server is provisioned to simulate the server team's environment. After creating vulnerabilities, an authenticated scan is performed, and the results are exported for future remediation steps.  

<img width="902" height="757" alt="image" src="https://github.com/user-attachments/assets/76e4267c-4070-49bf-ab29-bc81d8008269" />


---

### Step 6) Vulnerability Assessment and Prioritization

We assessed vulnerabilities and established a remediation prioritization strategy based on ease of remediation and impact. The following priorities were set:

1. Third Party Software Removal (Wireshark)
2. Windows OS Secure Configuration (Protocols & Ciphers)
3. Windows OS Secure Configuration (Guest Account Group Membership)
4. Windows OS Updates

---

### Step 7) Distributing Remediations to Remediation Teams

The server team received remediation scripts and scan reports to address key vulnerabilities. This streamlined their efforts and prepared them for a follow-up review.  

<img width="635" alt="image" src="https://github.com/user-attachments/assets/bbf9478f-e1d1-4898-846e-b510ec8c6f72">


---

### Step 8) Mock Meeting: Post-Initial Discovery Scan (Server Team)

The server team reviewed vulnerability scan results, identifying outdated software, insecure accounts, and deprecated protocols. The remediation packages were prepared for submission to the Change Control Board (CAB). 
# Vulnerability Scan Results Discussion

**Participants:**  
- Jimmy  
- Victoria  

---

**Victoria:** Good morning, Jimmy. How did the scan go? Any outages or resource issues?  

**Jimmy:** The scan completed smoothly. Resource utilization was minimal, and aside from the open connections, you wouldn’t have noticed it was running.  

**Victoria:** Excellent. Let’s move on to the findings.  

**Jimmy:** The majority of vulnerabilities are due to outdated versions of Wireshark installed on several servers. Additionally, I found that the local guest account is incorrectly part of the Administrators group, which poses a security risk.  

Some issues, such as Microsoft Edge (Chromium) vulnerabilities, may be resolved automatically through Windows Updates. Self-signed certificates can be ignored, but deprecated protocols (TLS 1.0/1.1) and weak cipher suites will require remediation.  

**Victoria:** So the priorities are:  
1. Remove outdated Wireshark installations.  
2. Correct the guest account group membership.  
3. Disable deprecated protocols and cipher suites.  

**Jimmy:** Correct. The good news is that these issues appear consistent across servers, so remediation should be uniform.  

**Victoria:** Do you foresee any challenges in addressing them?  

**Jimmy:** No major issues. We’ll run changes through the Change Control Board, but uninstalling Wireshark and removing the guest account should be straightforward. I’ll confirm with our systems administrators.  

**Victoria:** Great. Please prepare remediation packages to streamline deployment.  

**Jimmy:** Will do. Do you already have patch management in place for the Windows-related vulnerabilities?  

**Victoria:** Yes, patch management is active, so updates will be applied automatically.  

**Jimmy:** Perfect. I’ll research remediation steps and provide an update before the next Change Control Board meeting.  

**Victoria:** Sounds good. Thanks, Jimmy.  

**Jimmy:** Thank you, Victoria. Talk soon.  



### Step 9) Mock CAB Meeting: Implementing Remediations

The Change Control Board (CAB) reviewed and approved the plan to remove insecure protocols and cipher suites. The plan included a rollback script and a tiered deployment approach.  

# Vulnerability Remediation: Insecure Protocols & Cipher Suites

**Participants:**  
- Victoria (Risk Department)  
- Jimmy (Infrastructure Team)  

---

**Facilitator:** Next on the agenda are vulnerability remediations for the server team:  
1. Removal of insecure protocols.  
2. Removal of insecure cipher suites.  

Victoria from Risk has been working with Jimmy from Infrastructure on this. Jimmy, can you walk us through the technical aspects?  

**Jimmy:** Normally I would, but since Victoria built the solution, I’ll let her explain.  

**Victoria:** Sure. The issue is that insecure cipher suites and protocols remain enabled on some systems. If a server requests to use those outdated algorithms, our systems could still negotiate and use them, which is a security risk.  

The fix is straightforward: we wrote a PowerShell script that updates the Windows registry to disable deprecated protocols and ciphers, and enable only the secure, standardized ones currently in use.  

**Facilitator:** Sounds good. But what if something goes wrong? Do we have a rollback plan?  

**Victoria:** Yes. We’re approaching this with a tiered deployment:  
- **Pilot Group:** A small subset of systems.  
- **Pre-Production:** Wider testing.  
- **Full Production:** Organization-wide deployment.  

We’ve also developed automated rollback scripts. If issues arise, they restore the original registry values for protocols and ciphers.  

**Facilitator:** Excellent. Since these are simple registry updates, the risk is minimal. Any further questions?  

**(No further questions.)**  

**Facilitator:** Great. That concludes this week’s CAP meeting. See you all next week.  


---
### Step 10 ) Remediation Effort

#### Remediation Round 1: Outdated Wireshark Removal

The server team used a PowerShell script to remove outdated Wireshark. A follow-up scan confirmed successful remediation.  

<img width="946" height="742" alt="image" src="https://github.com/user-attachments/assets/132faed9-2c21-4eec-8f26-d5b70ef1dcaf" />


#### Remediation Round 2: Insecure Protocols & Ciphers

The server team used PowerShell scripts to remediate insecure protocols and cipher suites. A follow-up scan verified successful remediation, and the results were saved for reference.  

<img width="1163" height="628" alt="image" src="https://github.com/user-attachments/assets/7a7f7769-1265-41e3-9dfe-5a88bfd829ab" />


#### Remediation Round 3: Guest Account Group Membership

The server team removed the guest account from the administrator group. A new scan confirmed remediation, and the results were exported for comparison.  

<img width="1127" height="582" alt="image" src="https://github.com/user-attachments/assets/0d955c93-3170-4475-a70d-fc304ffed450" />


#### Remediation Round 4: Windows OS Updates

Windows updates were re-enabled and applied until the system was fully up to date. A final scan verified the changes  

<img width="1127" height="582" alt="image" src="https://github.com/user-attachments/assets/4789b2ca-d2ad-4e88-8e6f-36ec82309c5d" />

---

### First Cycle Remediation Effort Summary

The remediation process reduced total vulnerabilities by 80%, from 30 to 6. Critical vulnerabilities were resolved by the second scan (100%), and high vulnerabilities dropped by 90%. Mediums were reduced by 76%. In an actual production environment, asset criticality would further guide future remediation efforts.  

<img width="1920" alt="image" src="https://github.com/user-attachments/assets/51f0aae8-7f36-4d90-b29f-5257e57155f9">

[Remediation Data](https://docs.google.com/spreadsheets/d/1FTtFfZYmFsNLU6pm8nTzsKyKE-d2ftXzX_DPwcnFNfA/edit?gid=0#gid=0)

---

### On-going Vulnerability Management (Maintenance Mode)

After completing the initial remediation cycle, the vulnerability management program transitions into **Maintenance Mode**. This phase ensures that vulnerabilities continue to be managed proactively, keeping systems secure over time. Regular scans, continuous monitoring, and timely remediation are crucial components of this phase. (See [Finalized Policy](https://docs.google.com/document/d/1rvueLX_71pOR8ldN9zVW9r_zLzDQxVsnSUtNar8ftdg/edit?usp=drive_link) for scanning and remediation cadence requirements.)

Key activities in Maintenance Mode include:
- **Scheduled Vulnerability Scans**: Perform regular scans (e.g., weekly or monthly) to detect new vulnerabilities as systems evolve.
- **Patch Management**: Continuously apply security patches and updates, ensuring no critical vulnerabilities remain unpatched.
- **Remediation Follow-ups**: Address newly identified vulnerabilities promptly, prioritizing based on risk and impact.
- **Policy Review and Updates**: Periodically review the Vulnerability Management Policy to ensure it aligns with the latest security best practices and organizational needs.
- **Audit and Compliance**: Conduct internal audits to ensure compliance with the vulnerability management policy and external regulations.
- **Ongoing Communication with Stakeholders**: Maintain open communication with teams responsible for remediation, ensuring efficient coordination.

By maintaining an active vulnerability management process, organizations can stay ahead of emerging threats and ensure long-term security resilience.
