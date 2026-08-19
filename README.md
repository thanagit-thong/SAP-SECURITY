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
  - [X] Security on SAP ECS(RISE) 
- API and Integration Security
- Monitoring and Threat Detection
- Vulnerability and Patch Management
- AI Security for SAP
- Incident Response
- SAP Security Baselines
  - [x] sap-security-baseline.md
  - [x] system-hardening-checklist.md
- [SAP Security Plaform](#sap-security-platform)
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

### Composite Roles

### Derived Roles

## Naming Conventions

```text
Z_BASIS_ADMIN
Z_FI_ACCOUNTANT
Z_SD_DISPLAY
Z_HR_APPROVER
```

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

## Security Notes Management

### Discovery

### Risk Assessment

### Testing

### Deployment

### Validation

## Patch Governance

- Monthly Review
- Emergency Patch Process

## Vulnerability Scanning

- Infrastructure
- Operating System
- Database
- Applications

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
## SecurityBridge
## Onapsis

---
# SAP Security Community and Knowledge Sources
[x] SAP Insider
[X] [SAP Security Forum](https://pages.community.sap.com/topics/security)



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
