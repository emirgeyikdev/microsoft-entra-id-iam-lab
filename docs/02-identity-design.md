# Identity Architecture Design — EgeYik Labs

## 1. Purpose

This document defines the planned identity architecture for EgeYik Labs, a fictional enterprise Identity and Access Management (IAM) environment implemented using Microsoft Entra ID.

The architecture is designed to demonstrate enterprise identity administration, least privilege, role-based access control (RBAC), authentication security, and Conditional Access.

## 2. Organizational Structure

EgeYik Labs consists of five fictional departments with 23 planned employee identities.

| Department | Planned Employees |
|---|---:|
| IT & Security | 6 |
| Human Resources | 5 |
| Finance | 5 |
| Sales | 5 |
| Management | 2 |
| **Total** | **23** |

Dedicated laboratory administration and emergency access accounts are excluded from the planned employee count.

## 3. Identity Categories

### 3.1 Privileged Administration

A dedicated laboratory administrator account is responsible for initial tenant configuration and privileged administrative operations.

Global Administrator privileges will be restricted to authorized accounts.

### 3.2 Delegated IAM Administration

Alex Morgan will act as a delegated IAM administrator.

The account will receive only the administrative roles necessary to perform assigned IAM responsibilities.

Administrative access will be validated through positive and negative authorization tests.

### 3.3 Standard Employees

Standard employees will receive individual Microsoft Entra ID identities.

Their access will be based on departmental membership and defined business requirements.

Standard employees will not receive privileged Entra administrative roles by default.

### 3.4 Emergency Access

Emergency administrative access will be designed before restrictive Conditional Access policies are enforced.

Emergency access procedures, monitoring, and account exclusions will be documented and tested where supported.

## 4. Identity Naming Convention

Employee user principal names (UPNs) will follow this format:

`firstname.lastname@egeyiklabs.onmicrosoft.com`

Display names will follow this format:

`First Name Last Name`

All employee identities are fictional and created for laboratory testing.

## 5. Planned Security Groups

| Security Group | Purpose |
|---|---|
| SG-IT-Employees | IT & Security departmental membership |
| SG-HR-Employees | Human Resources departmental membership |
| SG-FIN-Employees | Finance departmental membership |
| SG-SALES-Employees | Sales departmental membership |
| SG-MGMT-Employees | Management departmental membership |
| SG-CA-Pilot | Conditional Access pilot testing |

Additional application-specific security groups will be defined during application access planning.

## 6. Access Control Principles

The identity architecture will follow these security principles:

- Least Privilege
- Role-Based Access Control (RBAC)
- Separation of Duties
- Individual Accountability
- Zero Trust
- Controlled Privileged Access

Departmental security groups will be used to organize and manage resource access where supported.

Microsoft Entra administrative roles will be managed separately from departmental application permissions.

## 7. Conditional Access Architecture

Conditional Access is a mandatory component of the planned security architecture.

Implementation requires appropriate Microsoft Entra ID licensing.

### Planned Policies

| Policy ID | Policy Name | Objective |
|---|---|---|
| CA-001 | Require MFA for Administrators | Protect privileged administrative access |
| CA-002 | Block Legacy Authentication | Prevent access through legacy authentication clients |
| CA-003 | Require MFA for Sensitive Applications | Strengthen access to selected enterprise applications |
| CA-004 | Location-Based Access Control | Evaluate sign-in access using defined network locations |
| CA-005 | Device-Based Access Control | Evaluate device-based access requirements where supported |

### Deployment Strategy

1. Define policy objectives and target identities.
2. Identify emergency access exclusions.
3. Configure policies in Report-only mode.
4. Evaluate policy results using What If and sign-in evidence.
5. Perform controlled pilot testing.
6. Enable selected policies after successful validation.
7. Document outcomes and rollback procedures.

## 8. Implementation Status

**Status:** Planned — not yet implemented.

This document describes the intended identity architecture. Actual configurations, role assignments, Conditional Access policies, and security validation results will be documented during subsequent project phases.

## 9. Disclaimer

EgeYik Labs is a fictional organization created for educational cybersecurity laboratory purposes. All employee identities and business scenarios are simulated.
