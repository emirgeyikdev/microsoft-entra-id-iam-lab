# Identity Architecture Design — EgeYik Labs

## 1. Purpose

This document defines the planned identity architecture for EgeYik Labs, a fictional enterprise IAM laboratory implemented with Microsoft Entra ID.

## 2. Organizational Structure

| Department | Planned Employees |
|---|---:|
| IT & Security | 6 |
| Human Resources | 5 |
| Finance | 5 |
| Sales | 5 |
| Management | 2 |
| **Total** | **23** |

The employee count represents the planned workforce and does not include dedicated laboratory administration or emergency access accounts.

## 3. Identity Categories

### Privileged Administration

The lab administrator account is responsible for tenant configuration, security policy management, and initial deployment.

Privileged access will be limited to authorized administrative accounts.

### Delegated IAM Administration

Alex Morgan will act as a delegated IAM administrator.

Administrative permissions will be selected according to job responsibilities and validated using positive and negative authorization tests.

### Standard Employees

Standard employees will receive individual identities and department-based security group memberships.

Administrative privileges will not be assigned unless explicitly required.

## 4. Identity Naming Convention

Employee user principal names will follow the format:

`firstname.lastname@egeyiklabs.onmicrosoft.com`

Display names will follow the format:

`First Name Last Name`

All employee identities are fictional.

## 5. Planned Security Groups

| Group | Purpose |
|---|---|
| SG-IT-Employees | IT & Security departmental membership |
| SG-HR-Employees | Human Resources departmental membership |
| SG-FIN-Employees | Finance departmental membership |
| SG-SALES-Employees | Sales departmental membership |
| SG-MGMT-Employees | Management departmental membership |
| SG-CA-Pilot | Conditional Access pilot testing |

Additional application-specific groups will be defined when application access requirements are finalized.

## 6. Privileged Access Principles

- Apply the principle of least privilege.
- Avoid assigning Global Administrator to standard employees.
- Separate business access requirements from Entra administrative roles.
- Validate delegated permissions through controlled tests.
- Design emergency administrative access before enforcing restrictive Conditional Access policies.

## 7. Conditional Access Design Considerations

Conditional Access policies will be introduced after appropriate Microsoft Entra ID licensing is available.

Initial policies will focus on:

1. Requiring MFA for privileged roles.
2. Blocking legacy authentication.
3. Requiring MFA for selected applications.
4. Testing location-based access conditions.
5. Evaluating device-based access conditions where supported.

Policies will be assessed in Report-only mode before controlled enforcement. Emergency access exclusions and rollback procedures will be documented.

## 8. Implementation Status

**Status:** Planned — not yet implemented.

This document describes the intended identity architecture. Actual deployment, group memberships, administrative role assignments, and security tests will be documented separately.
