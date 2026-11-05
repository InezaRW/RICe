## 1. Background

As part of our ISO/IEC 27001:2022 implementation, we need to have a solution that supports the employee lifecycle from joining the organization through employment changes and eventual termination.

The main ISO/IEC 27001:2022 controls this will supports are

- **A.6.1 - Screening**
- **A.6.2 - Terms and Conditions of Employment**
- **A.6.5 - Responsibilities After Termination or Change of Employment**

The objective is to have a consistent and traceable way to demonstrate that the relevant information-security activities have been addressed for each employee.

---

## 2. A.6.1 - Screening

The solution should provide an Employee Screening record for each employee.

The record should capture whether the required information is available and where the corresponding record/document can be found.

### Employee Information

| Information | Available |
|---|---|
| Employee Number | Yes |
| Full Name | Yes |
| Position / Role | Yes |
| Department / Team | Yes |
| Country | Yes |
| Employment Type | Yes |
| Start Date | Yes |

### Screening Information

| Screening Information | Available | Record / Document Link |
|---|---|---|
| National ID / Passport | Yes / No / N/A | Link |
| Academic Certificate(s) | Yes / No / N/A | Link |
| Tax ID | Yes / No / N/A | Link |
| Social Security ID | Yes / No / N/A | Link |
| Other Required Screening Information | Yes / No / N/A | Link |

The purpose is to record what information is available and where it is stored.

The screening record should not unnecessarily contain copies of sensitive documents.

---

## 3. A.6.2 - Terms and Conditions of Employment

The solution should also provide a way to record that the employee's applicable employment terms and information-security responsibilities have been addressed.

### Employment Requirements

| Employment Requirement | Available | Record / Document Link |
|---|---|---|
| Employment Agreement (Contract)| Yes / No / N/A | Link |
| Information-Security Responsibilities Included | Yes / No / N/A | Link |
| Applicable Policies / Conditions Acknowledged | Yes / No / N/A | Link |
| Other Required Employment Terms | Yes / No / N/A | Link |

The record should make it possible to identify the applicable employment agreement and supporting information-security requirements without unnecessarily duplicating the documents.

---

## 4. Onboarding Information

In addition to the three ISO controls above, I would like the same employee lifecycle solution to provide visibility over the main information-security onboarding activities.

### Account and Access Provisioning

| Account / Access | Available | Account / Record Link |
|---|---|---|
| Company Email | Yes / No / N/A | Link |
| Microsoft 365 | Yes / No / N/A | Link |
| GitHub Account | Yes / No / N/A | Link |
| GitHub Organization Access | Yes / No / N/A | Link |
| Azure / Entra ID | Yes / No / N/A | Link |
| MFA | Yes / No / N/A | Link |
| Other Required System Access | Yes / No / N/A | Link |

No passwords, access tokens, MFA secrets or recovery codes should be stored in the employee record.

### Equipment and Security Requirements

| Item | Available | Asset / Record Link |
|---|---|---|
| Laptop / Computer | Yes / No / N/A | Link |
| Internet router | Yes / No / N/A | Link |
| Mobile Phone | Yes / No / N/A | Link |
| Keyboard / Mouse | Yes / No / N/A | Link |
| Headset | Yes / No / N/A | Link |
| Other Assigned Asset | Yes / No / N/A | Link |
| Information Security Policy Acknowledged | Yes / No / N/A | Link |
| Information Security Training Completed | Yes / No / N/A | Link |
| Other Required Security Training | Yes / No / N/A | Link |

These onboarding items are not intended to redefine A.6.1.

They are included so that the employee lifecycle record can provide a single view of the relevant onboarding activities.

---

## 5. A.6.5 - Termination or Change of Employment

The same solution should support the end of employment or a change in employment or role.

For example, when an employee leaves or changes role, the record should be able to capture:

| Offboarding / Change Requirement | Status | Record / Evidence Link |
|---|---|---|
| Employment Change / Termination Recorded | Complete / Pending | Link |
| Access Review Performed | Complete / Pending | Link |
| Company Email Access Addressed | Complete / Pending | Link |
| Microsoft 365 Access Addressed | Complete / Pending | Link |
| GitHub Access Addressed | Complete / Pending | Link |
| Azure / Entra ID Access Addressed | Complete / Pending | Link |
| Other System Access Addressed | Complete / Pending | Link |
| MFA / Authentication Access Addressed | Complete / Pending | Link |
| Assigned Assets Returned / Addressed | Complete / Pending | Link |
| Information-Security Responsibilities After Termination / Change Addressed | Complete / Pending | Link |
| Other Required Offboarding Activities | Complete / Pending | Link |

The exact technical implementation and workflow can be determined based on the existing HR architecture.



## 7. Proposed Employee Lifecycle

My initial idea is to use GitHub Issues as the interface for HR and have the resulting information stored in the employee's record.

```mermaid
flowchart TD

    A["Employee Lifecycle"]
    A --> B["Onboarding"]
    B --> B1["A.6.1 Screening"]
    B --> B2["A.6.2 Terms & Conditions"]
    B --> B3["Account & Access Provisioning"]
    B --> B4["Equipment & Security Onboarding"]

    B4 --> C["During Employment"]
    C --> C1["Maintain Employee Record"]
    C --> C2["Applicable Screening Updates"]
    C --> C3["Employment Terms / Responsibilities"]

    C3 --> D["Employment Change"]
    D --> D1["Update Role / Employment Status"]
    D --> D2["Review Access"]
    D --> D3["Update Responsibilities"]

    D3 --> E["Termination / Offboarding"]
    E --> E1["A.6.5 Termination / Change"]
    E --> E2["Access Removal / Adjustment"]
    E --> E3["Asset Return"]
    E --> E4["Post-Employment Responsibilities"]

    E4 --> F["Employee Record"]
    F --> G["HR Repository"]

``````

---

