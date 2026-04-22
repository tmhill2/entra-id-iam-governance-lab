# Entra-ID-IAM-Lab

# Microsoft Entra ID IAM Lab – User & Access Management

## 📌 Overview

This project simulates a real-world IAM environment using Microsoft Entra ID, focusing on user provisioning, group-based access control, RBAC, Conditional Access (MFA), and Privileged Identity Management (PIM).
---

## 🧠 Objectives

* Create and manage users in Microsoft Entra ID
* Implement group-based access control (RBAC model)
* Assign users to department-based groups
* Investigate and troubleshoot access/permission issues

---

## 🏢 Environment

* Platform: Microsoft Entra ID
* Tenant Type: Cloud-based directory
* Access Level: Limited (non-admin user)

---

## 👤 User Provisioning

Created the following users to simulate employees:

* Sarah Johnson (HR)
* Mike Chen (IT)
* David Lee (Finance)

These users represent different departments within an organization.

---

## 👥 Group Management

Created security groups to organize access by department:

* HR Team
* IT Team
* Finance Team

Users were assigned to their respective groups to simulate real-world access management.

---

## 🔗 Group-Based Access Control

Instead of assigning permissions directly to users, access was structured using groups:

* Sarah Johnson → HR Team
* Mike Chen → IT Team
* David Lee → Finance Team

This approach reflects the principle of scalable and maintainable IAM design.

---

## 🔐 Role-Based Access Control (RBAC)

Attempted to assign administrative roles (e.g., User Administrator) to groups and users.

### 🚨 Result:

* Role assignment was not permitted due to insufficient privileges

### 🧠 Analysis:

This behavior demonstrates the principle of **least privilege**, where users are restricted from performing administrative actions unless explicitly granted permissions.

---

## 🚨 Troubleshooting Scenario

### Scenario:

A user (Sarah Johnson) required elevated permissions to manage users but was unable to perform administrative actions.

### Investigation Steps:

1. Verified user account exists
2. Confirmed group membership (HR Team)
3. Checked for assigned roles
4. Attempted role assignment

### 🔎 Root Cause Identified:
Lack of assigned administrative role and insufficient privileges to perform RBAC role assignment.

### Resolution:

* Identified that role assignment requires higher privileges (e.g., Global Administrator or User Administrator)
* Escalation would be required in a real-world scenario

---

## 📸 Screenshots

### Users Created
![Users](screenshots/all_users.png)

### Groups Created
![Groups](screenshots/groups_created.png)

### Group Membership
![Group Membership](screenshots/group_membership_hr.png)

### Role Assignment Limitation
![Roles](screenshots/roles_no_permission.png)

(Screenshots stored in `/screenshots` folder)

---

🔐 Conditional Access & MFA

To enhance security, a Conditional Access policy was implemented:

- Created policy: Require MFA for all users
- Applied to: All cloud applications
- Configured to require Multi-Factor Authentication (MFA)
- Excluded admin account to prevent lockout

🧪 Testing:
- Logged in as standard users
- Prompted for MFA setup using Microsoft Authenticator
- Successfully completed MFA challenge

📸 Screenshots
- ![MFA prompt during login](screenshots/MFA Prompt.png)
- ![Conditional Access policy configuration](screenshots/conditonal-access-policy.png)

---

🔐 Privileged Identity Management (PIM)

To enforce least privilege and just-in-time access:

- Removed permanent User Administrator role from Sarah Admin
- Assigned role as **Eligible** using PIM
- Required:
  - MFA
  - Justification
  - Time-bound activation

🧪 Testing:
- Logged in as Sarah Admin
- Navigated to PIM → My Roles
- Activated User Administrator role
- Completed MFA and justification
- Verified role changed from Eligible → Active

📸 Screenshots
- Eligible role assignment
- Role activation screen
- Active role with expiration time

## 🧠 Key Takeaways

* IAM should follow **group-based access control**, not direct user assignment
* Role-Based Access Control (RBAC) enforces permission boundaries
* The **principle of least privilege** restricts unauthorized actions
* Troubleshooting access issues requires validating users, groups, and roles

---

## 💼 Skills Demonstrated

* Identity and Access Management (IAM)
* User provisioning and lifecycle management
* Group-based access control
* RBAC analysis and troubleshooting
* Security best practices (least privilege)

---

## 🚀 Future Improvements

* Assign roles using an admin account
* Implement Conditional Access policies (MFA)
* Integrate with on-prem Active Directory (hybrid identity)
* Explore Privileged Identity Management (PIM)

## 🧩 Real-World Relevance

This lab reflects common IAM tasks performed in enterprise environments, including onboarding users, managing group-based access, and identifying permission issues related to RBAC restrictions. The inability to assign roles without proper privileges mirrors real-world least privilege enforcement and escalation workflows.
---
