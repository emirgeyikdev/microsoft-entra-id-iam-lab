# Business Requirements — EgeYik Labs

## 1. Organization Overview

EgeYik Labs is a fictional technology company used to simulate enterprise identity and access management scenarios.

The organization consists of 23 planned employee identities across five business units:

- IT & Security — 6 employees
- Human Resources — 5 employees
- Finance — 5 employees
- Sales — 5 employees
- Management — 2 employees

## 2. Project Objective

Design, implement, test, and document a secure enterprise Identity and Access Management (IAM) environment using Microsoft Entra ID.

The project will demonstrate identity administration, role-based access control, least privilege, authentication security, Conditional Access, and access validation.

## 3. Business Requirements

| ID | Requirement |
|---|---|
| BR-001 | Each employee must have an individual identity. |
| BR-002 | Departmental access must follow defined business responsibilities. |
| BR-003 | Administrative privileges must follow the principle of least privilege. |
| BR-004 | Privileged accounts must be protected by strong authentication. |
| BR-005 | Access to selected applications must be controlled and tested. |
| BR-006 | Employee onboarding, role changes, and offboarding must be documented. |
| BR-007 | Security-relevant changes and sign-ins must be auditable. |
| BR-008 | Conditional Access policies must be designed, tested, and validated. |
| BR-009 | Emergency administrative access must be considered before enforcing restrictive policies. |

## 4. Planned Technology Stack

- Microsoft Entra ID
- Microsoft Entra Role-Based Access Control
- Microsoft Entra Security Groups
- Microsoft Entra Conditional Access (P1/P2 licensing required)
- Microsoft Authenticator
- Microsoft Graph and PowerShell (where applicable)
- GitHub for documentation and version control

## 5. Success Criteria

The project will be considered complete when:

1. The planned identity and group architecture is implemented.
2. Administrative permissions are tested against documented requirements.
3. Authentication controls are validated.
4. Conditional Access policies are tested using supported tools and sign-in evidence.
5. Authorized and unauthorized access scenarios are documented.
6. Configuration evidence, architecture diagrams, and test results are published without exposing sensitive information.

## 6. Project Status

**Status:** In progress — architecture and planning.

**Environment:** Microsoft Entra ID Free. Conditional Access implementation is pending appropriate licensing.

## 7. Disclaimer

All employee identities, departments, and business scenarios are fictional and created for educational and cybersecurity laboratory purposes. This project does not represent a production organization.
