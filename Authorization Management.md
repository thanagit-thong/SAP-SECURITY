# Critical Authorizations – ABAP

```
SAP_ALL
SAP_NEW
S_DEVELOP
S_TABU_DIS and S_TABU_NAM
```
---
### SAP_ALL
```
[SECURITY ADVISORY]
```
---
### SAP_NEW
```
[SECURITY ADVISORY]
```
---
### S_DEVELOP
* ACTVT: 01/02
```
[SECURITY ADVISORY]

```

* ACTVT: 90
```
[SECURITY ADVISORY]
  It is generally not considered secure or a least-privilege approach to grant S_DEVELOP with ACTVT=90 broadly to anyone
including ABAP experts for debugging other users' sessions.

Granting this authorization can introduce several risks:

--------------------------------------------------------
1. Access to Sensitive Business Data
--------------------------------------------------------
When debugging another user's session, the debugger can inspect:
- Variables in memory
- Internal tables
- User input
- Business documents being processed
- Potentially sensitive information such as:
- Employee data
- Customer data
- Financial data
- Credentials or tokens temporarily held in memory

This may bypass normal business role segregation.

--------------------------------------------------------
2. Privilege Escalation Risks
--------------------------------------------------------
A skilled ABAP developer may:
- Manipulate variable values during debugging
- Bypass application checks
- Execute code paths not normally available
- Potentially perform transactions or updates beyond their business authorizations

The risk varies by SAP version and debugger restrictions.

--------------------------------------------------------
3. Segregation of Duties (SoD) Violations
--------------------------------------------------------
From an audit perspective (SOX, ISO 27001, NIS2, DORA, etc.):
- Developers should not have unrestricted access to production business data.
- Debugging production user sessions is often classified as a privileged activity.
- Auditors frequently challenge broad assignment of debugging permissions in Production.

--------------------------------------------------------
4. Data Privacy Concerns
--------------------------------------------------------
Debugging another user's session may expose:
- Personal data (GDPR)
- HR information
- Payroll data
- Customer confidential information

This creates privacy and compliance concerns.

```
```
[SECURE ALTERNATIVES]

Option 1: PAM ID or Firefighter ID (Recommended)
Option 2: Temporary Role Assignment
Option 3: Controlled Support Procedures such as Proactively monitor given user's activity 
```
```
[What does ACTVT=90 mean ?]

 In authorization object S_DEVELOP, activity 90 is commonly used for debugging.
Combined with appropriate development object values,
it can allow a user to debug programs and,
depending on the SAP release and configuration, attach to other users' sessions.

```
---
### S_TABU_DIS and S_TABU_NAM
