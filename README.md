# Red-Team Engagement Manual
A brief overview for the red-team engagement concept

> key to a successful engagement is well-coordinated planning and communication through all parties involved
> 

*THM*

## Engagement Varieties

- Tabletop exercises
- Adversary emulation
- Physical assessment

can be categorized between a general internal/network penetration test or a focused adversary emulation

## Scoping

*Define Objectives and Scopes within the clients enterprise structure e.g.*

Example 1 - Global Enterprises:

**Objectives:**

1. Identify system misconfigurations and network weaknesses.
    1. Focus on exterior systems.
2. Determine the effectiveness of endpoint detection and response systems.
3. Evaluate overall security posture and response.
    1. SIEM and detection measures.
    2. Remediation.
    3. Segmentation of DMZ and internal servers.
4. Use of white cards is permitted depending on downtime and length.
5. Evaluate the impact of data exposure and exfiltration.

**Scope:**

1. System downtime is not permitted under any circumstances.
    1. Any form of DDoS or DoS is prohibited.
    2. Use of any harmful malware is prohibited; this includes ransomware and other variations.
2. Exfiltration of PII is prohibited. Use arbitrary exfiltration data.
3. Attacks against systems within 10.0.4.0/22 are permitted.
4. Attacks against systems within 10.0.12.0/22 are prohibited.
5. Bean Enterprises will closely monitor interactions with the DMZ and critical/production systems.
    1. Any interaction with "*.bethechange.xyz" is prohibited.
    2. All interaction with "*.globalenterprises.thm" is permitted.

# ROE (Rules of Engagement)

[Red Team Development and Operations](https://redteam.guide/docs/checklists/red-team-checklist/)

## Engagement Documentation

**Engagement Plan:**

| Component | Purpose |
| --- | --- |
| CONOPS (Concept of Operations) | Non-technically written overview of how the red team meets client objectives and target the client. |
| Resource plan | Includes timelines and information required for the red team to be successful—any resource requirements: personnel, hardware, cloud requirements. |

**Operations Plan:**

| Component | Purpose |
| --- | --- |
| Personnel | Information on employee requirements. |
| Stopping conditions | How and why should the red team stop during the engagement. |
| RoE (optional) | - |
| Technical requirements | What knowledge will the red team need to be successful. |

**Mission Plan:**

| Component | Purpose |
| --- | --- |
| Command playbooks (optional) | Exact commands and tools to run, including when, why, and how. Commonly seen in larger teams with many operators at varying skill levels. |
| Execution times | Times to begin stages of engagement. Can optionally include exact times to execute tools and commands. |
| Responsibilities/roles | Who does what, when. |

**Remediation Plan (optional):**

| Component | Purpose |
| --- | --- |
| Report | Summary of engagement details and report of findings. |
| Remediation/consultation | How will the client remediate findings? It can be included in the report or discussed |

## Rules of engagement:

"official" document in the engagement planning process and requires proper authorization between the client and the red team

(format and wording of the RoE are critical since it is a legally binding contract and sets clear expectations)

### Standard sections:

| Section Name | Section Details |
| --- | --- |
| Executive Summary | Overarching summary of all contents and authorization within RoE document |
| Purpose | Defines why the RoE document is used |
| References | Any references used throughout the RoE document (HIPAA, ISO, etc.) |
| Scope | Statement of the agreement to restrictions and guidelines |
| Definitions | Definitions of technical terms used throughout the RoE document |
| Rules of Engagement and Support Agreement | Defines obligations of both parties and general technical expectations of engagement conduct |
| Provisions | Define exceptions and additional information from the Rules of Engagement |
| Requirements, Restrictions, and Authority | Define specific expectations of the red team cell |
| Ground Rules | Define limitations of the red team cell's interactions |
| Resolution of Issues/Points of Contact | Contains all essential personnel involved in an engagement |
| Authorization | Statement of authorization for the engagement |
| Approval | Signatures from both parties approving all subsections of the preceding document |
| Appendix | Any further information from preceding subsections |

### Executive Summary

The Rules of Engagement (ROE) document the approvals, authorizations, and critical implementation issues necessary to execute the engagement. Signing of the ROE constitutes acknowledgement and approval of the customer, system owner, and Red Team of the Red Team’s authorities in execution of the engagement.

**The objectives include:**
• Monitor security posture and response
      • Focus on internal systems and insider threats
• Assess the response of the defense team
• Assess ability to move laterally through internal infrastructure
• Employ physical penetration testing to assess onsite security posture

**Explicit Restrictions:**
• Use of white cards are strictly prohibited
• Any form of DDoS or DoS is prohibited
• Attacks against any system within 192.168.1.0/24 is prohibited

**Authorized Target Space:**

• 10.0.4.0/22
• *.bethechange.xyz, *.globalenterprises.thm 

**Activities:**
• Reconnaissance
• Access Types
• Phishing
• Physical and social engineering

• Positioning
• Assumed breach scenario

• Impact

## CONOPS

******************Concept of operations******************

components that should be included in a CONOPS:

- Client Name
- Service Provider
- Timeframe
- General Objectives/Phases
- Other Training Objectives (Exfiltration)
- High-Level Tools/Techniques planned to be used
- Threat group to emulate (if any)

## **CONOPS real example:**

Holo Enterprises has hired TryHackMe as an external contractor to conduct a month-long network infrastructure assessment and security posture. The campaign will utilize an assumed breach model starting in Tier 3 infrastructure. Operators will progressively conduct reconnaissance and attempt to meet objectives to be determined. If defined goals are not met, the red cell will move and escalate privileges within the network laterally. Operators are also expected to execute and maintain persistence to sustain for a period of three weeks. A trusted agent is expected to intervene if the red cell is identified or burned by the blue cell throughout the entirety of the engagement. The last engagement day is reserved for clean-up and remediation and consultation with the blue and white cell.

The customer has requested the following training objectives: assess the blue team's ability to identify and defend against live intrusions and attacks, Identify the risk of an adversary within the internal network. The red cell will accomplish objectives by employing the use of Cobalt Strike as the primary red cell tool. The red cell is permitted to use other standard tooling only identifiable to the targeted threat.

Based on customer security posture and maturity, the TTPof the threat group: FIN6, will be employed throughout the engagement.

## Resource Plan:

**dates, knowledge required, etc.**

(Not as summary instead a bullet list)

- Header
    - Personnel writing
    - Dates
    - Customer
- Engagement Dates
    - Reconnaissance Dates
    - Initial Compromise Dates
    - Post-Exploitation and Persistence Dates
    - Misc. Dates
- Knowledge Required (optional)
    - Reconnaissance
    - Initial Compromise
    - Post-Exploitation
- Resource Requirements
    - Personnel
    - Hardware
    - Cloud
    - Misc.

### Example:

| RED CELL LEAD: Cryillic ENGAGEMENT DATES: 10/12/21 - 11/12/21 | ASST CELL LEAD: Simpuki CLIENT POC: Bean Enterprises |
| --- | --- |
| Execution Dates | Resource Summary |
| Reconnaissance: 10/04/2021-10/14/2021Initial Access: 10/14/2021-10/24/2021Post-Exploitation and Persistence: 10/24/2021 - 11/14/2021Remeditation: TBDMiscellaneous: n/a | The red cell has requested the needed resources outlined in the following document.Any further resources needed by any teams or operators should create a revised resource plan and submit to the client representatives for approval. |
| Personnel Requirements | Hardware Requirements |
| 1. One Red Cell Lead(s)
2. One Red Cell Assistant Lead(s)
3. Three Red Cell Operators | 1. No hardware is required for this engagement, all machine resources will be allocated to the cloud |
| Cloud Requirements | Misc. Requirements |
| 1. Red Cell will send expense report of cloud costs to client after engagement
2. Red Cell is requesting a budget of $1000 for AWS cloud costs | 1. No other requirements are currently projected |

## Operations Plan:

(No standard)

- Header
    - Personnel writing
    - Dates
    - Customer
- Halting/stopping conditions (can be placed in ROE depending on depth)
- Required/assigned personnel
- Specific TTPs and attacks planned
- Communications plan
    - (Possible options)
    - [vectr.io](http://vectr.io/)
    - Email
    - Slack
- Rules of Engagement (optional)

### Example plan:

(Thought of from client/business perspective)

| RED CELL LEAD: Cryillic ENGAGEMENT DATES: 10/12/21 - 11/12/21 | ASST CELL LEAD: Simpuki CLIENT POC: Bean Enterprises |
| --- | --- |
| Engagement Objectives |  |
| 1. Identify system misconfigurations and network weaknesses
2. Determine the effectiveness of endpoint detection and response systems
3. Evaluate overall security posture and response
4. Evaluate impact of data exposure and exfiltration |  |
| Halting/Stopping Conditions | Communications Plan |
| 1. In the event of a system outage all engagement operations will cease
2. In the event of an operator being burnt, information will be kept on a need to know basis
3. In the event any evidence of an actual attack is found all operations will cease and an investigation will begin | Throughout the engagement the red cell will utilize vectr.io to communicate internally and with the client: "Bean Enterprises". The client will be given a daily update on the engagement and debriefed on progress and occurences. If any stopping conditions are encountered the red cell will consult with the client immediately upon discovery. Contact information for all teams and cells and members of the engagement can be found within the ROE document. |
| Planned TTPs and Attacks |  |
| 1. Due to the discovery of email addresses in the reconnaissance phase, spearphishing via mshta and typosquatted domains will be employed in the initial access phase.
2. To assess detection capabilites the red cell will employ process masquerading and signed binary proxy execution.
3. To sustain the engagement the red cell will employ the use of C2 infrastructure through HTTP/HTTPS protocols, data encoding, and ingress tools.
4. To keep C2 domains and infrastructure alive domain generation algorithms will be employed during initial access and persistence. |  |

## Mission plan:

(Details the exact actions)

Minimum details that cells should include into the plan:

- Objectives
- Operators
- Exploits/Attacks
- Targets (users/machines/objectives)
- Execution plan variations

### Example Plan:

(Thought of from operator perspective)

| RED CELL LEAD: Cryillic ENGAGEMENT DATES: 10/12/21 - 11/12/21 | ASST CELL LEAD: Simpuki CLIENT POC: Bean Enterprises |
| --- | --- |
| Engagement Objectives |  |
| 1. Identify system misconfigurations and network weaknesses
2. Determine the effectiveness of endpoint detection and response systems
3. Evaluate overall security posture and response
4. Evaluate impact of data exposure and exfiltration |  |
| Engagement Breakdown |  |
| 1. Use the email address list found from osint to craft a spearphishing target wordlist. Use the mshta payload found in our internal repositories. Consult leads for help using domain generation algorithms with spearphishing. Phishing campaign will last from 10/13/2021-10/23/2021. Report success rate to team leads to submit to vectr.io.
2. Consult with team lead and use tooling found in internal repository to maintain access and setup needed tool infrastructure |  |
| Targets | Execution Variants |
| • External Targets
    1. BEAN-MAIL
    2. BEAN-PROD
    3. bethebean.com
    4. 10.10.6.29
• Internal Targets
    1. Determine internal targets with team leads after initial access | • In the event of any varying events throughout the engagement, immediately contact a team lead and disuss how to continue. |

*this is a brief concept: 

**remember that your number 1 goal is to meet the client's objectives**
