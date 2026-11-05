# Security Group Implementation

## 1. Objective

The objective of this phase was to implement a department-based security group structure in Microsoft Entra ID for EgeYik Labs, a fictional organization with 23 planned employee identities across five departments.

The groups establish a foundation for centralized identity management, controlled group membership, and future access assignments.

## 2. Implemented Security Groups

Five cloud-based security groups were created in Microsoft Entra ID.

| Department | Security Group | Membership Type |
|---|---|---|
| IT & Security | SG-IT-Employees | Assigned |
| Human Resources | SG-HR-Employees | Assigned |
| Finance | SG-Finance-Employees | Assigned |
| Sales | SG-Sales-Employees | Assigned |
| Management | SG-Management-Employees | Assigned |

All groups were configured with:

- **Group type:** Security
- **Membership type:** Assigned
- **Source:** Cloud
- **Initial direct members:** 0

## 3. Implementation Approach

The groups were created through the Microsoft Entra admin center under **Entra ID > Groups > All groups**.

Each group was configured with a department-specific name and description following a consistent naming convention.

The `SG-` prefix identifies a security group, while the department name identifies its intended organizational scope.

### Why Security Groups?

Security groups were selected to support the organization of employee identities and future assignment of access permissions to supported resources.

### Why Assigned Membership?

Assigned membership was selected to allow administrators to explicitly control which employees belong to each department group.

This approach supports transparent membership management and allows group assignments to be verified during the user provisioning phase.

## 4. Verification

Following implementation, each group was inspected in the Microsoft Entra admin center.

The following properties were verified:

- Correct group name and department description
- Security group type
- Assigned membership type
- Cloud source
- Zero initial direct members

The **All groups** view was also inspected to confirm that all five department security groups existed in the tenant.

At this stage, the groups provide organizational structure only. Employee membership assignments and access-control testing will be performed in subsequent phases.

## 5. Implementation Evidence

The following screenshots document the implementation:

| Evidence | Description |
|---|---|
| [IT Security Group](../evidence/phase-02/02-it-security-group.png) | IT & Security group configuration |
| [HR Security Group](../evidence/phase-02/03-hr-security-group.png) | Human Resources group configuration |
| [Finance Security Group](../evidence/phase-02/04-finance-security-group.png) | Finance group configuration |
| [Sales Security Group](../evidence/phase-02/05-sales-security-group.png) | Sales group configuration |
| [Management Security Group](../evidence/phase-02/06-management-security-group.png) | Management group configuration |
| [All Security Groups](../evidence/phase-02/07-all-security-groups.png) | Verification of all five department groups |

Sensitive identifiers and personal account information were redacted from the publicly shared evidence.

## 6. Security Considerations

Department-based security groups help establish a manageable structure for identity and access management.

However, security group membership does not automatically grant Microsoft Entra administrative roles.

Administrative permissions will be configured separately using Microsoft Entra role-based access control (RBAC), following the principle of least privilege.

Access assignments and effective permissions will be tested in later phases.

## 7. Outcome

Successfully implemented and verified five department-based Microsoft Entra ID security groups for EgeYik Labs.

The environment is now prepared for employee user provisioning and department-based group membership assignments.
