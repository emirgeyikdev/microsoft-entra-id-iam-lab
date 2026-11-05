# Employee Directory — EgeYik Labs

## 1. Overview

This document defines 23 fictional employee identities planned for the EgeYik Labs Microsoft Entra ID environment.

The employee directory serves as the reference for user provisioning, departmental security group membership, and access control testing.

## 2. IT & Security

| ID | Name | Job Title |
|---|---|---|
| IT-01 | Alex Morgan | IAM Administrator |
| IT-02 | Daniel Carter | IT Manager |
| IT-03 | Ethan Brooks | Security Analyst |
| IT-04 | Olivia Reed | Helpdesk Specialist |
| IT-05 | Noah Bennett | IT Support |
| IT-06 | Sophia Turner | Systems Engineer |

## 3. Human Resources

| ID | Name | Job Title |
|---|---|---|
| HR-01 | Emma Wilson | HR Manager |
| HR-02 | Mia Anderson | HR Specialist |
| HR-03 | Liam Parker | Recruiter |
| HR-04 | Ava Mitchell | HR Coordinator |
| HR-05 | Grace Collins | HR Assistant |

## 4. Finance

| ID | Name | Job Title |
|---|---|---|
| FIN-01 | James Walker | Finance Manager |
| FIN-02 | Charlotte Harris | Senior Accountant |
| FIN-03 | Benjamin Scott | Financial Analyst |
| FIN-04 | Amelia Cooper | Accountant |
| FIN-05 | Henry Adams | Finance Assistant |

## 5. Sales

| ID | Name | Job Title |
|---|---|---|
| SALES-01 | William Evans | Sales Manager |
| SALES-02 | Isabella Young | Sales | Sales Manager |
| SALES-03 | Lucas King | Sales Representative |
| SALES-04 | Harper Wright | Sales Representative |
| SALES-05 | Mason Hill | Sales Coordinator |

## 6. Management

| ID | Name | Job Title |
|---|---|---|
| MGMT-01 | Alexander Foster | CEO |
| MGMT-02 | Victoria Hayes | Operations Director |

## 7. Identity Provisioning Standards

All employee identities will follow these standards:

- User principal name: `firstname.lastname@egeyiklabs.onmicrosoft.com`
- Display name: `First Name Last Name`
- Department: Assigned business department
- Job title: Assigned fictional position
- Account type: Member
- Department security group: Assigned according to department

Privileged Entra roles will be assigned only where required and validated separately.

## 8. Administrative Accounts

The dedicated laboratory administrator account is separate from the 23 planned employee identities.

Alex Morgan is included in the employee directory and will be used to test delegated IAM administration.

Emergency administrative access will be designed and documented before restrictive Conditional Access policies are enforced.

## 9. Implementation Status

**Status:** Planned.

No employee provisioning or group membership is claimed by this document. Implementation evidence will be recorded during the deployment phase.
