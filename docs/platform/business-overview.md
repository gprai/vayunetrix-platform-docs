# Business Overview

VayuNetrix AWS Platform is a guided AWS platform engineering product for customers that want a structured AWS foundation without turning every engagement into a custom consulting exercise.

The business goal is simple: help a customer select the AWS platform capabilities they need, understand the package and approval path, safely create or operate the environment, and receive evidence that governance, security, drift, remediation, and cost controls are being handled.

## How The Product Is Sold And Used

The commercial entry point is the VayuNetrix parent website:

- Website: [www.vayunetrix.com](https://www.vayunetrix.com)
- Parent website repo: [gprai/vayunetrix](https://github.com/gprai/vayunetrix)

The parent website is responsible for customer-facing business steps:

- registration and email confirmation
- product discovery
- package and capability selection
- pricing, quote, order, and subscription status
- customer command center
- support entry
- product launch into the AWS Platform portal

The AWS Platform portal is the product workspace:

- Portal: [aws-platform.vayunetrix.com](https://aws-platform.vayunetrix.com)
- API: [api.aws-platform.vayunetrix.com](https://api.aws-platform.vayunetrix.com)
- Private implementation repo: [gprai/aws-platform-engineering](https://github.com/gprai/aws-platform-engineering)

The portal receives a signed handoff from the parent website. After that handoff, the customer sees the workspace and only the capabilities their selected package allows.

## Problem

Many organizations struggle with the same AWS foundation questions:

- How many AWS accounts do we need?
- Which regions should be enabled?
- How should workloads, security, shared services, sandbox, and exception accounts be separated?
- Who approves account creation, network changes, security baseline changes, and remediation?
- How do we prove governance and security are working?
- How do we detect drift and decide what is safe to fix automatically?
- How do we show cost by account, team, environment, application, or cost center?

AWS services such as Organizations, Control Tower, IAM Identity Center, GuardDuty, Security Hub, Config, CloudTrail, and Terraform are powerful. Customers still need a guided operating layer around them.

## Product Vision

VayuNetrix provides a guided platform creation and operations experience:

1. The customer signs in through the parent website.
2. The customer selects AWS Platform Engineering and chooses the package/capabilities they want.
3. The parent website owns quote, order, subscription, and entitlement status.
4. The AWS Platform portal opens through a signed product handoff.
5. The portal guides intake, architecture, validation, approval, execution status, evidence, governance, security, drift, remediation, and cost views.
6. Sensitive customer artifacts stay in the customer-controlled connector/runtime boundary.

## Value For Customers

- Faster AWS foundation planning.
- Safer provisioning with review and approval gates.
- Clear package-to-capability boundaries.
- Repeatable governance and security checks.
- Drift detection and remediation workflows.
- Cost visibility by team, environment, application, and account.
- Audit evidence without manually assembling screenshots and command output.
- Productized onboarding instead of scattered scripts and one-off setup.

## Product Family Direction

VayuNetrix is expanding beyond AWS Platform Engineering. The next product under development is GateForge:

- GateForge repo: [gprai/GateForge](https://github.com/gprai/GateForge)
- Planned launch path: [www.vayunetrix.com/GateForge](https://www.vayunetrix.com/GateForge)

GateForge is focused on approved infrastructure templates, Terraform plan review, policy checks, named approvals, controlled apply, and audit evidence for regulated engineering teams.

