
# Security Group Membership Implementation

## Objective

Implement department-based security group membership in Microsoft Entra ID for EgeYik Labs.

The objective is to establish a structured foundation for group-based access management, supporting future role-based access control (RBAC) and least-privilege access policies.

## Environment

- **Identity platform:** Microsoft Entra ID
- **Tenant:** `egeyiklabs.onmicrosoft.com`
- **Employee identities:** 23
- **Security groups:** 5
- **Group type:** Security
- **Membership type:** Assigned
- **Identity source:** Cloud-only

## Group Membership Design

Each employee was assigned to the security group corresponding to their business department.

| Security Group | Department | Members |
|---|---|---:|
| `SG-IT-Employees` | IT & Security | 6 |
| `SG-HR-Employees` | Human Resources | 5 |
| `SG-Finance-Employees` | Finance | 5 |
| `SG-Sales-Employees` | Sales | 5 |
| `SG-Management-Employees` | Management | 2 |
| **Total** | **5 departments** | **23** |

The two administrative/lab accounts were excluded from these employee groups.

## Implementation

Group membership assignments were configured through the Microsoft Entra admin center:

`Entra ID > Groups > All groups > [Security Group] > Members > Add members`

The following implementation approach was used:

1. Opened each department's existing security group.
2. Selected the employee identities defined in the employee directory.
3. Added the employees as direct group members.
4. Reviewed the Direct members list.
5. Verified that the membership count and employee names matched the department design.

No administrative directory roles were assigned as part of this process.

## Verification Results

All five security groups were reviewed after membership assignment.

| Security Group | Expected | Verified | Result |
|---|---:|---:|---|
| `SG-IT-Employees` | 6 | 6 | Pass |
| `SG-HR-Employees` | 5 | 5 | Pass |
| `SG-Finance-Employees` | 5 | 5 | Pass |
| `SG-Sales-Employees` | 5 | 5 | Pass |
| `SG-Management-Employees` | 2 | 2 | Pass |
| **Total** | **23** | **23** | **Pass** |

The member names in each group matched the planned department assignments. No unexpected members appeared in the reviewed lists.

## Evidence

The following screenshots document the final group membership configurations:

- [IT & Security — 6 Members](../evidence/phase-02/11-it-group-members.png)
- [Human Resources — 5 Members](../evidence/phase-02/12-hr-group-members.png)
- [Finance — 5 Members](../evidence/phase-02/13-finance-group-members.png)
- [Sales — 5 Members](../evidence/phase-02/14-sales-group-members.png)
- [Management — 2 Members](../evidence/phase-02/15-management-group-members.png)

## Security Considerations

### Department-Based Identity Organization

Employees are organized into security groups based on their business departments, providing a consistent structure for future access assignments.

### Least Privilege Foundation

Department group membership does not automatically grant Microsoft Entra administrative privileges.

Administrative role assignments and access permissions must be configured separately according to the RBAC design.

### Separation of Administrative Accounts

The lab administrator and lab owner identities are excluded from employee department groups.

### Access Control Readiness

The groups can be used as the basis for future access policies and resource assignments.

However, group membership alone does not demonstrate that application access restrictions or least-privilege permissions are enforced.

## Implementation Status

**Completed:** Department security group membership assignments for all 23 employee identities.

**Pending:** Administrative RBAC configuration, authentication security controls, and access validation testing.
