# Customer Journey

![VayuNetrix customer workflow](../../diagrams/vayunetrix-customer-workflow.svg)

## Journey Overview

The customer journey now starts at the VayuNetrix parent website and moves into the AWS Platform portal only after the customer has a valid product selection and signed handoff.

```text
www.vayunetrix.com
-> register and confirm email
-> choose AWS Platform Engineering
-> select package and capabilities
-> preview quote/order/subscription status
-> launch product portal
-> signed handoff to aws-platform.vayunetrix.com
-> Workspace Home
-> guided intake, approval, execution, evidence, and operations
```

## Step-By-Step Journey

1. Visit [www.vayunetrix.com](https://www.vayunetrix.com).
2. Register and confirm email.
3. Open the customer command center.
4. Choose AWS Platform Engineering.
5. Select package and capabilities.
6. Review quote/order/subscription status.
7. Launch the AWS Platform portal through signed handoff.
8. Land in AWS Platform Workspace Home.
9. Connect the customer-controlled local workspace when execution is needed.
10. Validate intake or upload the approved workbook.
11. Review plan, cost, security, and blast-radius impact.
12. Approve changes.
13. Watch live operation status.
14. Review governance, security, drift, remediation, cost, and evidence summaries.
15. Continue operating through dashboards, alerts, approvals, and reports.

## Workspace Experience

After handoff, the AWS Platform Workspace Home summarizes:

- selected product/package
- enabled capabilities
- AWS setup progress
- current risk status
- pending approvals
- latest operation status
- cost/governance/security evidence summaries
- connector and local workspace status when applicable

## Guided Architecture Builder

The architecture builder asks guided questions about:

- business size
- regions and data residency
- environments
- account model
- governance level
- security baseline
- networking pattern
- cost controls

The builder should not expose capabilities that the active package does not allow. A learning package should see a simpler experience than an enterprise package.

## Approval-Centric Operations

Before high-impact actions, the platform shows:

- what will change
- affected roots, accounts, OUs, regions, and services
- security impact
- cost impact
- blast-radius summary
- required approvals

This keeps provisioning and remediation deliberate rather than automatic and opaque.
