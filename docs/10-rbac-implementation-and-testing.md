# Phase 3 — RBAC Implementation and Security Testing

## 1. Overview

This phase focuses on implementing and validating role-based access control (RBAC) in the EgeYik Labs Microsoft Entra ID environment.

The primary objective is to delegate identity administration responsibilities while applying the principle of least privilege.

The validation covers user provisioning, password reset operations, audit log visibility, and access restrictions.

## 2. Environment and Scope

| Component | Configuration |
|---|---|
| Tenant | `egeyiklabs.onmicrosoft.com` |
| Identity platform | Microsoft Entra ID |
| License | Microsoft Entra ID Free |
| Test administrator | Alex Morgan |
| Assigned roles | User Administrator, Reports Reader |
| Role assignment scope | Directory / organization |
| Test account | `rbac-test-user@egeyiklabs.onmicrosoft.com` |

Testing was performed using the delegated administrator account rather than the Global Administrator account.

## 3. Administrative Role Implementation

Alex Morgan was assigned two Microsoft Entra ID administrative roles.

### User Administrator

The User Administrator role delegates selected identity management operations, including standard user creation and permitted password resets.

### Reports Reader

The Reports Reader role provides read-only access to supported identity reports and monitoring information.

Both roles were assigned directly to Alex Morgan at the directory scope.

**Evidence:** [Administrative role assignment](../evidence/phase-03/01-user-administrator-assignment.png)

## 4. RBAC Test Results

| Test ID | Test scenario | Observed result | Status |
|---|---|---|---|
| RBAC-001 | Standard user creation | User successfully created | PASS |
| RBAC-002 | Password reset | Password successfully reset | PASS |
| RBAC-005 | Audit logs access | Audit records successfully displayed | PASS |
| RBAC-006 | Conditional Access restriction | Overview access denied with HTTP 401 | PASS — limited scope |

### RBAC-001 — Standard User Creation

**Objective:** Validate the delegated administrator's ability to create a standard user.

**Action:** Alex Morgan created the account `rbac-test-user@egeyiklabs.onmicrosoft.com`.

**Observed result:** The user account was created successfully, and the operation was recorded in the directory audit logs.

**Status:** PASS

**Evidence:**
- [User creation confirmation](../evidence/phase-03/02-rbac-001-user-creation-success.png)
- [User creation audit log](../evidence/phase-03/03-rbac-001-user-creation-audit-log.png)

### RBAC-002 — Password Reset

**Objective:** Verify that the delegated administrator can reset the password of an eligible standard user.

**Action:** Alex Morgan initiated a password reset for the RBAC test account.

**Observed result:** Microsoft Entra ID confirmed that the password reset was successful.

**Status:** PASS

**Evidence:** [Password reset confirmation](../evidence/phase-03/04-rbac-002-password-reset-audit-log.png)

### RBAC-005 — Audit Logs Access

**Objective:** Validate the delegated administrator's ability to view directory audit information.

**Action:** Alex Morgan accessed the Audit logs section in Microsoft Entra ID.

**Observed result:** Directory audit records were displayed successfully.

**Status:** PASS — audit log visibility confirmed.

**Validation limitation:** The test account held both User Administrator and Reports Reader roles. Therefore, this result confirms access under the combined role configuration but does not independently verify the permissions granted by Reports Reader.

**Evidence:** [Audit logs access](../evidence/phase-03/05-rbac-005-audit-logs-access.png)

### RBAC-006 — Conditional Access Access Restriction

**Objective:** Evaluate access to the Conditional Access management interface using the delegated administrator account.

**Action:** Alex Morgan attempted to access Conditional Access Overview.

**Observed result:** Microsoft Entra ID displayed "You don't have access" with HTTP error 401 and the message "Insufficient privileges to complete the operation."

**Status:** PASS — access to the tested page was denied.

**Validation limitation:** This test confirms that the Conditional Access Overview page was inaccessible in the tested session. It does not independently establish whether the administrator could create, modify, or delete Conditional Access policies. Microsoft Entra ID Free licensing also limits the available testing scope.

**Evidence:** [Conditional Access access denied](../evidence/phase-03/06-rbac-006-conditional-access-denied.png)

## 5. Security Findings

The completed validation produced the following observations:

- Delegated administration successfully supported standard user provisioning.
- Password reset functionality was available for the eligible test account.
- The delegated administrator could view directory audit records.
- Access to Conditional Access Overview was denied.
- Administrative permissions were evaluated using a dedicated account instead of relying on Global Administrator privileges.

These findings demonstrate selected RBAC behaviors in the configured environment. They do not represent an exhaustive assessment of all administrative permissions.

## 6. Limitations and Future Improvements

The following areas remain outside the completed validation scope:

- Independent verification of the Reports Reader role.
- Comprehensive testing of privileged role assignment restrictions.
- Conditional Access policy creation, modification, and deletion.
- Advanced identity governance capabilities requiring additional licensing.

The temporary RBAC test account should be removed when it is no longer needed for subsequent testing.

## 7. Conclusion

Phase 3 implemented delegated administrative role assignments and validated selected Microsoft Entra ID identity management and access control behaviors.

The results are supported by screenshots and audit evidence, with testing limitations documented explicitly.

Subsequent phases will focus on authentication security, identity lifecycle management, and additional security controls.
