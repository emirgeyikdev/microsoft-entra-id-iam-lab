
# User Provisioning Implementation

## Objective
Provision 23 fictional employee identities in Microsoft Entra ID for EgeYik Labs, establishing a consistent identity structure across five business departments.

## Environment
- Identity platform: Microsoft Entra ID
- Tenant domain: `egeyiklabs.onmicrosoft.com`
- Identity source: Cloud-only
- Provisioning method: Manual user creation through Microsoft Entra admin center
- Employee account type: Member

## Provisioning Standards
All employee identities were configured using the following standards:

| Attribute | Configuration |
|---|---|
| User principal name | `firstname.lastname@egeyiklabs.onmicrosoft.com` |
| Display name | First name and last name |
| User type | Member |
| Department | Assigned according to the employee directory |
| Job title | Assigned according to the employee directory |
| Account status | Enabled |
| Usage location | United States (fictional lab scenario) |
| Initial password | Automatically generated |
| Security group membership | Deferred to the group membership implementation phase |
| Administrative roles | No new administrative roles assigned during provisioning |

No passwords or authentication secrets are stored in this repository.

## Department Distribution

| Department | Provisioned Employees | Security Group |
|---|---:|---|
| IT & Security | 6 | `SG-IT-Employees` |
| Human Resources | 5 | `SG-HR-Employees` |
| Finance | 5 | `SG-Finance-Employees` |
| Sales | 5 | `SG-Sales-Employees` |
| Management | 2 | `SG-Management-Employees` |
| **Total** | **23** | **5 security groups** |

The planned identities and job titles are documented in [Employee Directory](03-employee-directory.md).

## Administrative and Lab Accounts
The tenant also contains two administrative/lab identities that are excluded from the 23-employee directory:

- **Lab Administrator:** Dedicated account used for tenant configuration and lab administration.
- **Lab owner account:** Separate account used to manage the lab environment.

These identities are not treated as business department employees. Therefore, the expected tenant user count is **25 accounts: 23 employee identities and 2 administrative/lab identities**.

The existence of these accounts does not imply that employee identities have been assigned administrative privileges.

## Implementation Process
1. Created cloud-only employee identities through `Entra ID > Users > New user > Create new user`.
2. Configured user principal names, display names, departments, job titles, and usage locations according to the employee directory.
3. Kept employee accounts enabled and classified as Member users.
4. Deferred security group memberships and administrative role assignments to subsequent implementation phases.
5. Reviewed the tenant-wide user list after provisioning.

## Verification and Evidence
The Microsoft Entra ID **All users** view displayed **25 total accounts**, consistent with the expected 23 employees and 2 administrative/lab accounts.

The user list was captured in two screenshots because the complete list could not fit in a single view:

- [All Users — Part 01](../evidence/phase-02/09-all-users-part-01.png)
- [All Users — Part 02](../evidence/phase-02/10-all-users-part-02.png)

A representative employee account configuration was captured separately:

- [Employee User Configuration](../evidence/phase-02/08-user-configuration.png)

## Security Considerations
- Business job titles do not automatically grant Microsoft Entra administrative roles.
- Employee identities are separated conceptually from administrative/lab identities.
- Security group assignments will be implemented and verified separately.
- Authentication secrets are excluded from GitHub evidence and documentation.
- Personally identifying lab owner details are redacted from public screenshots where appropriate.

## Implementation Status
**Employee identity provisioning completed.** Security group membership assignments and access-control validation are pending.
