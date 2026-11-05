# Tenant Environment & Baseline — EgeYik Labs

## 1. Purpose

This document describes the initial Microsoft Entra ID tenant environment used for the EgeYik Labs enterprise IAM laboratory.

The baseline was captured before implementing the planned departmental security groups, employee provisioning, delegated administrative roles, and Conditional Access policies.

## 2. Tenant Overview

| Property | Baseline Value |
|---|---|
| Tenant Display Name | EgeYik Labs |
| Identity Platform | Microsoft Entra ID |
| Microsoft Entra Plan | Entra Free |
| Tenant Type | Cloud-based laboratory |
| Directory Synchronization | Microsoft Entra Connect disabled |
| Employee Identity Model | Cloud-only identities |
| Planned Workforce | 23 fictional employees |

## 3. Initial Environment Baseline

| Resource | Observed Count |
|---|---:|
| Users | 3 |
| Groups | 2 |
| Devices | 0 |
| Applications | 0 |

These values represent the environment at the time of the baseline screenshot and may change as implementation progresses.

## 4. Administrative Identity Model

The laboratory uses a dedicated tenant administration account for configuration and security administration.

A separate personal administrator account was present during baseline capture.

The planned delegated IAM administrator, Alex Morgan, will be provisioned or verified during the identity implementation phase.

Administrative role assignments will be reviewed and validated before implementing restrictive security policies.

## 5. Authentication and Conditional Access

The environment currently uses Microsoft Entra Free.

Conditional Access implementation is a mandatory project objective and requires appropriate Microsoft Entra ID P1 or P2 licensing.

Before enforcing Conditional Access policies, the project will establish a safe administrator access and recovery strategy.

Conditional Access configuration, testing, and deployment evidence will be documented in subsequent phases.

## 6. Baseline Security Posture

The Microsoft Entra admin center displayed an Identity Secure Score of 73.68% during baseline capture.

This score is a point-in-time observation and does not independently establish the security effectiveness of the environment.

## 7. Evidence

- `evidence/phase-02/01-tenant-overview.png` — Microsoft Entra tenant overview, captured before implementation.

Sensitive identifiers and personal information must be redacted before publishing screenshots.

## 8. Implementation Status

**Status:** Baseline documented. Employee provisioning, group implementation, RBAC validation, and Conditional Access deployment are pending.

## 9. Disclaimer

EgeYik Labs is a fictional organization used exclusively for educational identity and cybersecurity laboratory activities.
