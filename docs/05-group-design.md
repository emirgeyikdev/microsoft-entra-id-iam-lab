# Security Group Design — EgeYik Labs

## 1. Purpose

This document defines the planned Microsoft Entra ID security group architecture for EgeYik Labs.

The design supports departmental organization, access management, and controlled Conditional Access pilot testing.

## 2. Group Naming Convention

Security groups will follow a consistent naming convention:

`SG-DEPARTMENT-PURPOSE`

Examples:

- `SG-IT-Employees`
- `SG-HR-Employees`
- `SG-FIN-Employees`
- `SG-SALES-Employees`
- `SG-MGMT-Employees`

The Conditional Access pilot group will use the name `SG-CA-Pilot`.

## 3. Planned Security Groups

| Group Name | Type | Membership | Planned Members |
|---|---|---|---:|
| SG-IT-Employees | Security | Assigned | 6 |
| SG-HR-Employees | Security | Assigned | 5 |
| SG-FIN-Employees | Security | Assigned | 5 |
| SG-SALES-Employees | Security | Assigned | 5 |
| SG-MGMT-Employees | Security | Assigned | 2 |
| SG-CA-Pilot | Security | Assigned | Selected test users |

The pilot group is an additional security group. Its members may also belong to departmental groups.

## 4. Membership Rules

- Each employee will belong to the appropriate departmental security group.
- Membership will be assigned based on the employee directory.
- Department transfers will require membership review.
- Offboarding will include removal or revocation of applicable access.
- Administrative privileges will not be granted solely through departmental membership.

## 5. Conditional Access Pilot Group

The `SG-CA-Pilot` group will be used to test Conditional Access policies with selected laboratory identities.

Before enforcement:

1. Identify pilot users.
2. Define policy scope and exclusions.
3. Confirm emergency administrative access.
4. Evaluate policies in Report-only mode.
5. Review sign-in results and expected outcomes.
6. Enable policies only after successful testing.

Conditional Access implementation requires appropriate Microsoft Entra ID licensing.

## 6. Group Administration

Groups will initially use assigned membership.

Group ownership and membership changes will be documented and validated.

Application-specific groups may be added when application access requirements are finalized.

## 7. Implementation Status

**Status:** Planned — not yet deployed.

This document describes the intended group architecture. Actual group creation, memberships, access assignments, and test evidence will be documented during implementation.

## 8. Disclaimer

All identities and organizational structures are fictional and used for educational laboratory purposes.
