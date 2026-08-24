# SAP Security Best Practices Knowledge Base
A community-driven repository of SAP Security, Authorization, Basis Security, Cloud Security, API Security, AI Security, and Compliance best practices.



---

# Table of Contents 
- [Introduction](#introduction)
- Security Governance
- Identity and Access Management
- Authorization Management
- Authentication Security
- SAP Basis Security
- SAP Hana Security
- SAP Fiori Security
- SAP BTP Security
- SAP Cloud Application Security
  - [X] Cloud-security-checklist.md
  - [X] Security on SAP ECS (RISE) 
- API and Integration Security
- Monitoring and Threat Detection
- [Vulnerability and Patch Management](#vulnerability-and-patch-management)
- AI Security for SAP
- Incident Response
- SAP Security Baselines
  - [x] sap-security-baseline.md
  - [x] system-hardening-checklist.md
- [SAP Security Platform](#sap-security-platform)
- [SAP Security Community and Knowledge Sources](#sap-security-community-and-knowledge-sources)
- [Quick Reference Library](#quick-reference-library) 
- [Contributing](#contributing)
- [Disclaimer](#disclaimer)

---
# Introduction
## **Objectives**
- Share SAP Security best practices
- Establish security baseline recommendations
- Provide implementation guidance
- Support auditors, architects, and administrators
- Encourage community collaboration


## **Audience**
- SAP Security Consultants
- SAP Basis Administrators
- IAM Teams
- Security Architects
- Auditors
- Compliance Officers
- CISOs


## Guiding Principles
- Least Privilege
- Separation of Duties
- Zero Trust
- Secure by Design
- Defense in Depth
---

# Security Governance

## Security Policy Framework

- Information Security Policy
- Access Control Policy
- Password Policy
- Emergency Access Policy (PAM/FireFighter)
- Logging and Monitoring Policy


## Security Metrics

- Privileged Users
- SoD Violations
- Critical Authorizations
- Patch Compliance
- Audit Findings

---

# SAP Security Architecture

## Landscape Design

- Development
- Quality Assurance
- Pre-Production
- Production

## Network Segmentation

- Internal Zone
- DMZ
- SAP Router
- Reverse Proxy

## Secure Transport Management

- Transport Approval Workflow
- Emergency Transports
- Change Management Controls

## Environment Segregation

- Developer Separation
- Administrator Separation
- Production Access Restrictions

---

# Identity and Access Management

## User Lifecycle Management (JML)

### Joiner
- User Provisioning
- Initial Access Assignment

### Mover
- Access Review
- Role Adjustment

### Leaver
- Access Removal
- User Locking

## Identity Governance
- Role Ownership
- Access Certification
- Quarterly Reviews

## Privileged Access Management
- Firefighter IDs
- Emergency Access
- Session Monitoring
- Approval Workflow

---

# Authorization Management

## Authorization Concepts

- Least Privilege
- Need-to-Know
- Role-Based Access Control

## Role Design Standards

### Single Roles
Task/Functional Roles (Single Roles) is the atomic unit of role design. 
A role contains a limited, highly specific set of transaction codes (T-codes) or Web Dynpros required to perform exactly one business task (e.g., Maintain Vendor Master or Approve Purchase Orders).

### Composite Roles
Real-world business titles mapped to HR profiles. 
A composite role contains zero native transactions. 
It acts purely as a container bundling multiple Functional and Enabler roles together (e.g., "US Accounts Payable Clerk")

### Conceptual Framework: Parent vs Child (Master Roles vs Derived Roles)
The Master and Derived Role methodology is a native inheritance framework within the SAP Profile Generator (PFCG). 
It serves as an alternative approach to the 3-Tier (Enabler) model. 
This design is highly effective for organizations with low-to-medium organizational variation across locations, 
as it structures roles through a parent-child template relationship.

**Master Role (The Parent/Template):** 
This role defines what a user can do. It houses the menus, Transaction Codes (T-codes), reports, Web Dynpros, and authorization objects. 
Crucially, organizational levels (such as Company Code, Plant, or Sales Organization) are left blank or unmaintained. Master roles must never be directly assigned to end-users.

**Derived Role (The Child/Instance):** 
This role inherits the exact functional layout (menus, T-codes, objects) from its designated Master role. 
The only components defined uniquely inside a Derived role are its explicit Organizational Levels. 
When a Master role is updated and pushed, it overwrites the authorizations of all child roles while preserving their unique location data.


## Critical Authorization Objects

```text
S_USER_AGR
S_USER_GRP
S_USER_PRO
S_RFC
S_TABU_DIS
S_TABU_NAM
S_DEVELOP
S_PROGRAM
S_TCODE
```

## Segregation of Duties (SoD)

### Procure to Pay

### Order to Cash

### Record to Report

### Hire to Retire

## Access Reviews

- Monthly
- Quarterly
- Annual

---

# Authentication Security

## Password Security

### Recommended Parameters

```text
login/min_password_lng
login/password_expiration_time
login/fails_to_user_lock
login/password_history_size
```

## Multi-Factor Authentication

- SAP GUI
- Fiori
- SAP Cloud Solutions

## Single Sign-On

- Kerberos
- SAML 2.0
- Microsoft Entra ID
- Identity Authentication Service (IAS)

## Certificate Management

- PKI Design
- Certificate Renewal
- Trust Configuration

---

# SAP Basis Security

## System Hardening

- Secure Installation
- Remove Default Accounts
- Secure Services

## Security Parameters

```text
rdisp/gui_auto_logout
login/min_password_lng
auth/rfc_authority_check
```

## RFC Security

- Trusted RFC Review
- RFC User Restrictions
- Technical User Governance

## Gateway Security

### secinfo

### reginfo

### gw/acl_mode

## OS Security

- File Permissions
- Service Accounts
- Logging

## Database Security

- Privileged Access
- Encryption
- Audit Logging

---

# SAP HANA Security

## User Management

## Role Management

## Audit Policies

## Encryption

### Data at Rest

### Data in Transit

## Sensitive Data Protection

- Masking
- Anonymization

## Backup Security

- Encrypted Backups
- Access Controls

---

# SAP Fiori Security

## Fiori Architecture

## Catalog Security

## Group Security

## Space and Page Security

## OData Service Security

## Launchpad Hardening

## Fiori Access Reviews

---

# SAP BTP Security
## Guideline
SAP provides [SAP BTP Security Recommendations](https://help.sap.com/docs/btp/sap-btp-security-recommendations-c8a9bb59fe624f0981efa0eff2497d7d/sap-btp-security-recommendations) at 304 topics (as of 08/2026) to harden BTP . It can be mapped with Secure Operations Map as well.

## Global Account Security

## Subaccount Security

## Role Collections

## Identity Authentication Service (IAS)

## Identity Provisioning Service (IPS)

## Cloud Connector Security

## Secret Management

## Tenant Security

---

# SAP Cloud Application Security
- [X] Cloud-security-checklist.md

- [X] Security on SAP ECS (RISE)

## LogServ & RAVEN
<img width="1192" height="655" alt="image" src="https://github.com/user-attachments/assets/08e05d92-3806-4b6a-b1c3-a37fc23473f1" />

### LogServ
Referring to this [nice article by Jatin Tiwari](https://www.linkedin.com/posts/jatin-tiwari999_sap-logserv-sap-logserv-is-an-optional-share-7405256037907234817-EDwl/)
```text
SAP LogServ is an optional RISE with SAP / SAP Enterprise Cloud Services (ECS) offering that centralizes infrastructure, OS, database, and SAP layer logs and forwards them to your SIEM or log platform; enablement mainly revolves around contracting it, selecting log scope, and integrating with tools like Microsoft Sentinel or Splunk. 

What SAP LogServ ✔️  
SAP LogServ is an ECS service for collection, storage, forwarding, and access of logs from all SAP-managed systems in RISE with SAP (OS, DB, application, network, etc.).​
It is purchased as an additional managed service on top of RISE and is intended to restore the log visibility customers lose when SAP operates the infrastructure layer.​

```
SAP provided [LogServ introduction video](https://sapvideo.cfapps.eu10-004.hana.ondemand.com/?entry_id=1_4gufcxqa) (57m) as well 

How ECS Security Portal looks like:
<img width="1467" height="625" alt="image" src="https://github.com/user-attachments/assets/a27135f8-3f4b-449d-b859-781129850a0e" />

Sample log from LogServ in JSON:
<img width="1687" height="307" alt="image" src="https://github.com/user-attachments/assets/525221ca-e7a7-477a-b193-ea647f01a489" />

more information about [LogServe](https://community.sap.com/t5/enterprise-resource-planning-blog-posts-by-members/ultimate-blog-series-sap-logserv-integration-with-microsoft-sentinel/ba-p/14126401)

## RAVEN (Risk and Vulnerability Engine)

Sample Dashboard from RAVEN:
<img width="1681" height="586" alt="image" src="https://github.com/user-attachments/assets/507c127c-8992-4813-91e2-8c4f11f4827d" />
<img width="1680" height="835" alt="image" src="https://github.com/user-attachments/assets/fad5602a-f360-47b8-b6b3-d700e297a055" />
<img width="1689" height="802" alt="image" src="https://github.com/user-attachments/assets/0969b463-a875-45d2-8c43-148743125f1b" />
<img width="1693" height="767" alt="image" src="https://github.com/user-attachments/assets/313d4a91-c0f6-4a46-8e02-8845aa076ee0" />
<img width="1571" height="705" alt="image" src="https://github.com/user-attachments/assets/1affb659-7e20-41cc-a510-b4b4f1eafaa6" />

<sub>*Image Source: SAP Security Web Cast - LogServ&Raven Demo 20.08.2026*</sub>

## SAP SuccessFactors

- RBP Governance
- MFA
- Integration Security

## SAP Ariba

- User Access Reviews
- Supplier Access Governance

## SAP Concur

- Administrator Controls
- Audit Logging

## SAP Analytics Cloud

- Workspace Security
- Data Access Controls

## SAP Datasphere

- Data Access Governance
- Sharing Controls

---

# API and Integration Security

## SAP Integration Suite

## API Authentication

- OAuth2
- Mutual TLS
- Certificate Authentication

## API Security Best Practices

- Token Lifecycle Management
- Secrets Management
- Encryption Standards

## Secure Integrations

- SAP to SAP
- SAP to Non-SAP
- Third-Party Integrations

## API Monitoring

- Authentication Failures
- Abuse Detection
- Rate Limiting

---

# Monitoring and Threat Detection

## SAP Security Audit Log

## HANA Audit Log

## BTP Audit Log

## SIEM Integration

- Microsoft Sentinel
- Splunk
- QRadar

## Detection Use Cases

### Privilege Escalation

### Emergency Access Misuse

### Sensitive Table Access

### RFC Abuse

### Failed Login Attacks

### Suspicious Configuration Changes

---

# Vulnerability and Patch Management

Continuous review of system Vulnerability and Patch Management promotes ISO 27001 framework:
- Vulnerability management
- Patch management
- Secure operations


## Security Notes Management

### STEP 1: Discovery
The objective is to understand the current security posture, identify missing SAP Security Notes (patches), assess risks, and establish a remediation strategy before implementation.
The primary goals are:

- Identify all SAP systems in scope.
- Determine current patch levels.
- Discover missing SAP Security Notes.
- Identify vulnerable software components.
- Assess business and technical risks.
- Prioritize remediation activities.
- Build a Security Note remediation roadmap.

**Sources and Tools**
1. Monthly SAP Security Patch Day
2. Transaction code SNOTE
3. SOLUTION MANAGER: System Recommendations (sunset by end of 2027)
4. Cloud ALM: CSA SAP Note
   CALM CSA "Recommended Security Notes" is another SAP effort to replace SYSREC.
   <img width="1362" height="292" alt="image" src="https://github.com/user-attachments/assets/41eb1621-66ea-4cef-b576-28e0efdaa2f5" />
   At the time of writing this one (08/2026), this tool was just released with very simply UI.
   It shows only relevant notes that affect respective system, but unable to provide comment or change status like in SYSREC. <BR>
   <BR>
   Find more detail at [Calculate Security Notes](https://help.sap.com/docs/cloud-alm/applicationhelp/calculating-security-notes)<BR>
   <img width="450" height="222" alt="image" src="https://github.com/user-attachments/assets/fc616bea-f722-4f8b-9264-d546bfedbb9e" />
   >NOTE: <BR>
   >If you don't see **Calculate Security Notes** button, assure that you have authorization **Security Notes Viewer** assigned to your SID by CALM Admin.
    
5. SAP RISE 

###  STEP 2: Risk Assessment

###  STEP 3: Realization

###  STEP 4: Summary Report


## Patch Governance

- Monthly Review: Define KPI for each severity and criticality. Keep in mind that higher CVSS may not pose higher risk than lower CVSS. True criticality depends on your system configurations and asset sensitivity.
  Just use CVSS as guide, but never ignore low CVSS one.
- Monthly cycle: 
  1. Second Tuesday is Security patch day, but not limied to. SAP may publish emergency security patch anytime if it's a serious one.
  2. Follow through 3-step approach: DISCOVERY --> RISK ASSESSMENT --> REALIZATION --> SUMMARY REPORT

- Emergency Patch Process
  
Emergency Patch SLA Recommendation<BR>
<img width="600" height="210" alt="image" src="https://github.com/user-attachments/assets/62689254-2559-4302-a291-0cc96fa82d22" />



## Vulnerability Scanning Scope
- Infrastructure
- Operating System
- Database
- Applications

## Key Success Criteria
✅ Complete SAP landscape visibility<BR>
✅ 100% identification of missing Security Notes<BR>
✅ Risk-based prioritization rather than patch-count prioritization<BR>
✅ Alignment with ISO 27001, NIST CSF, DORA, and NIS2 requirements<BR>
✅ Executive-approved remediation plan<BR>

---

# Data Protection and Privacy

## Data Classification

- Public
- Internal
- Confidential
- Restricted

## Data Access Controls

## Encryption Requirements

## Data Retention

## GDPR Compliance

## Data Masking

## Test Data Protection

---

# AI Security for SAP

## AI Governance

## SAP Joule Security

## Prompt Security

## AI Data Protection

## AI Risk Management

## Third-Party AI Integration Security

## AI Compliance

- ISO 42001
- EU AI Act

---

# Compliance and Regulatory Mapping

## ISO 27001

### Access Control

### Logging

### Vulnerability Management

### Incident Management

## NIST Cybersecurity Framework

### Govern

### Identify

### Protect

### Detect

### Respond

### Recover

## NIS2

## DORA

## SOX

## GDPR

---

# Incident Response

## SAP Security Incident Process

### Preparation

### Detection

### Analysis

### Containment

### Eradication

### Recovery

### Lessons Learned

## Incident Playbooks

### Unauthorized Access

### Data Breach

### Privilege Escalation

### Malware

### Ransomware

### Insider Threat

---

# Security Baselines

## SAP S/4HANA Security Baseline

## SAP HANA Security Baseline

## SAP Fiori Security Baseline

## SAP BTP Security Baseline

## Cloud Application Baselines

### SuccessFactors

### Ariba

### Concur

### SAC

### Joule

---
# SAP Security Platform
- [x] [SecurityBridge](https://securitybridge.com/)
- [x] [Onapsis](https://onapsis.com/)
- [x] [Layer7](https://www.layersevensecurity.com/)
- [X] [Xiting](https://xiting.com/en/)
- [X] [SAP Enterprise Threat Detection (ETD)](https://www.sap.com/products/financial-management/enterprise-threat-detection.html)
- [X] [SAP Cloud ALM - CSA](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/configuration-security-analysis/csa-content.html?isu_page=1)

## ADVANTAGE OF HAVING EXTRA PLATFORM  
Traditional cyber security tools are blind to the inner workings of an SAP ecosystem.
Standard security solutions (like generic Firewalls, Antivirus, or traditional SIEMs) monitor network traffic and operating systems but cannot read or interpret SAP-specific protocols (like RFC, DIAG), application logs, or ABAP code. Without a dedicated SAP security platform, your core business data sits in a massive security blind spot.

Here is a detailed breakdown of why these platforms are necessary to safeguard an SAP environment:

### 1. Eliminating the Security Blind Spot (Context-Aware Monitoring)
- **SAP Logs are Cryptic:** SAP generates massive volumes of proprietary logs. 
Traditional SIEMs cannot contextualize this data, leading to missed critical events or overwhelming "alert fatigue.
- **Log Enrichment:** Some platforms specialize in parsing, correlation, and translating complex SAP logs into actionable security insights that your main Security Operations Center (SOC) can actually understand.

### 2. Securing Custom Code (ABAP Security)
- **The Backdoor Risk:** Most enterprises write millions of lines of custom code (ABAP) to tailor SAP to their business.
Traditional application security scanners cannot analyze ABAP code for vulnerabilities.
- **DevSecOps Integration:** Tools like SecurityBridge and Layer Seven Security scan custom code during development and before it hits production, preventing developers from accidentally introducing vulnerabilities, data leaks, or malicious backdoors.

### 3. Real-Time Threat Detection & Behavioral Analysis
- **Insider Threats:** A large portion of SAP breaches involve internal users abusing high privileges or executing unauthorized data downloads.
- **Exploit Prevention:** These platforms look for anomalous behavior, such as sudden privilege escalation or unauthorized Remote Function Calls (RFC).
For unpatched systems, some platforms offer "virtual patching" to block known exploits at the network level until a permanent SAP Note can be applied.

### 4. Automated Vulnerability & Patch Management
- **Complexity of SAP Notes:** SAP releases security patches (SAP Security Notes) every month.
Manually reviewing, testing, and applying these across dozens of SAP landscapes is time-consuming.
- **Continuous Assessment:** These platforms automatically scan your entire SAP landscape for misconfigurations, default passwords, open ports, and missing patches, prioritizing them based on actual business risk.

### 5. Continuous Audit & Compliance (SOX, GDPR, NIS2)
- **Automated Evidence Collection:** Preparing for a financial or data privacy audit manually takes weeks of extracting tables and user lists.
- **Segregation of Duties (SoD):** These platforms continuously monitor compliance frameworks, ensuring that users do not have conflicting roles (e.g., the ability to both create a vendor and approve a payment) and flag unauthorized emergency access (Firefighter IDs) instantly.

## HOW TO KICKSTART
If you have budget constraint, or you are a lone wolf in SAP Security Operations, starting with [SAP Cloud ALM CSA (Configuration & Security Analysis)](https://support.sap.com/en/alm/sap-cloud-alm/operations.html?isu_page=1&anchorId=section_881666798) is a low hanging fruit without surprise invoice after you.
Cloud ALM is free (until certain level) with low configuration effort. 
Check out [Note 3499485](https://me.sap.com/notes/0003499485):
```text
-------------------------------------------
What is the cost of SAP Cloud ALM?
-------------------------------------------
  No license or subscription fee is required for SAP Cloud ALM. According to the usage rights, customers with 
SAP Cloud Service subscriptions containing Enterprise Support, cloud editions, with SAP Enterprise Support, 
or with Product Support for Large Enterprises are entitled to use one SAP Cloud ALM tenant per customer 
number free of charge. This includes a baseline of 24 GB SAP HANA Memory and a baseline of 24 GB 
monthly outbound API data transfer. 
```

Up until the demand from corporate cybersecurity and/or ITGC auditor is higher, 
.. or your SAP Security Operations team grow up, 
.. or you encounter with cybersecurity challenges which force you to go beyonds what Cloud ALM can serve.  
Then it's time to change your tool on hands to be anything more advance like SecurityBridge, Onapsis, Layer7, ETD, etc.

---
# SAP Security Community and Knowledge Sources
- [x] [SAP Insider](https://copenhagen.sapinsider.org/)
- [X] [SAP Security Forum](https://pages.community.sap.com/topics/security)
- [X] Recommended articles:
  - [SAP Security Awareness: The Control You Can’t Configure](https://www.linkedin.com/pulse/sap-security-awareness-control-you-cant-configure-peter-doyle-tnnle/)
  - [SAP Security: The Foundation of Secure and Compliant SAP Landscapes](https://www.linkedin.com/pulse/sap-security-foundation-secure-compliant-landscapes-sonawane-hc17f/)
  - [Beyond Compliance: SAP Security as Strategic Advantage](https://www.linkedin.com/pulse/beyond-compliance-sap-security-strategic-advantage-jarod-sandham-9fsue/)
  - [Why I’m Writing About SAP Security (and What I’ll Focus On)](https://www.linkedin.com/pulse/why-im-writing-sap-security-what-ill-focus-peter-doyle-46kpe/)
  - [Hardening SAP: The 10 Most Common Misconfigurations (and How to Fix Them)](https://www.linkedin.com/pulse/hardening-sap-10-most-common-misconfigurations-how-fix-peter-doyle-ympue/)
    
---
# Checklists and Templates

## Security Review Checklist

## Go-Live Security Checklist

## System Hardening Checklist

## Role Design Checklist

## Access Review Checklist

## Firefighter Access Checklist

## Vulnerability Assessment Template

## Risk Assessment Template

## Security Exception Template

---

# Quick Reference Library
- [x] [Note 2191612_: Use of Security Audit Log as of NetWeaver 7.50](https://me.sap.com/notes/2191612)

## Critical Transactions

```text
SU01
SU24
SU25
PFCG
SM19
SM20
SM59
SCC4
SE16N
SE38
SA38
RSAU_CONFIG
RZ10
RZ11
STMS
DBACOCKPIT
```

## Critical Tables

```text
USR02
USR04
AGR_USERS
AGR_1251
UST04
UST12
RFCDES
TSTCA
USRACL
```

## Critical Authorization Objects

```text
S_TCODE
S_RFC
S_TABU_DIS
S_TABU_NAM
S_USER_GRP
S_USER_AGR
S_USER_PRO
S_DEVELOP
S_PROGRAM
S_DATASET
```

## Useful SAP Security Reports

```text
RSUSR003
RSUSR008_009_NEW
RSUSR200
RSUSR070
RSPFPAR
```

---

# Contributing

## Contribution Guidelines

- Follow repository standards
- Use references where possible
- Update changelog
- Submit pull request

## Review Process

1. Submit Pull Request
2. Technical Review
3. Security Validation
4. Approval
5. Publish

---

# Disclaimer

> This repository is provided for educational and informational purposes only.
> All content is provided "AS IS" without warranty of any kind.
> Users are responsible for validating recommendations in their own SAP environments.
> Contributors and maintainers shall not be held liable for any direct or indirect damages resulting from the use of this content.
