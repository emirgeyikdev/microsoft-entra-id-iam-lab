# RBAC & Access Control Matrix — EgeYik Labs

## 1. Purpose

This document defines the planned administrative role assignments and access control requirements for the EgeYik Labs Microsoft Entra ID laboratory.

The design follows the principle of least privilege and separates directory administration from business application access.

## 2. Administrative Identity Model

| Identity | Responsibility | Planned Privileges |
|---|---|---|
| Lab Administrator | Tenant configuration and security administration | Global Administrator |
| Alex Morgan | Delegated identity administration | User Administrator, Reports Reader |
| Standard Employees | Business operations | No Entra administrative roles |

Emergency access accounts will be documented separately before restrictive Conditional Access policies are enforced.

## 3. Planned Administrative Access Matrix

| Administrative Operation | Lab Administrator | Alex Morgan | Standard Employee |
|---|---|---|---|
| Create standard users | Allowed | Allowed | Denied |
| Reset standard user passwords | Allowed | Allowed, within role limitations | Denied |
| Manage supported security groups | Allowed | Allowed, within role limitations | Denied |
| View supported sign-in and audit reports | Allowed | Allowed, subject to permissions | Denied by administrative role model |
| Assign Global Administrator role | Allowed | Denied | Denied |
| Manage Conditional Access policies | Allowed | Denied | Denied |

The matrix represents intended permissions. Actual access will be verified through controlled authorization tests.

## 4. Department-Based Application Access

| Department | HR Application | Finance Application | Sales Application |
|---|---|---|---|
| IT & Security | Denied | Denied | Denied |
| Human Resources | Allowed | Denied | Denied |
| Finance | Denied | Allowed | Denied |
| Sales | Denied | Denied | Allowed |
| Management | Not assigned by default | Not assigned by default | Not assigned by default |

Application access will be implemented using appropriate Microsoft Entra ID groups and supported application assignment controls.

These are planned authorization requirements, not yet deployed application permissions.

## 5. Planned RBAC Validation Tests

| Test ID | Test Scenario | Expected Result |
|---|---|---|
| RBAC-001 | Alex creates a standard user | Allowed |
| RBAC-002 | Alex resets a standard user's password | Allowed |
| RBAC-003 | Alex attempts to assign Global Administrator | Denied |
| RBAC-004 | Standard employee attempts privileged administration | Denied |
| RBAC-005 | Alex views supported audit reports | Allowed |
| RBAC-006 | Alex attempts to manage Conditional Access policies | Denied |

All tests will be executed using authorized laboratory accounts.

## 6. Security Principles

- Least Privilege
- Separation of Duties
- Role-Based Access Control
- Individual Accountability
- Controlled Privileged Access
- Regular Access Review

## 7. Implementation Status

**Status:** Planned — pending deployment and validation.

Administrative roles and access permissions described in this document are design targets. Actual role assignments, test results, and supporting evidence will be recorded during the implementation phase.

## 8. Disclaimer

All employees and business applications are fictional and used exclusively for educational laboratory testing.
