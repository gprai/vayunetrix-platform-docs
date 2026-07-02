# FAQ

## What is VayuNetrix AWS Platform?

VayuNetrix AWS Platform is a guided AWS platform engineering product. It helps customers plan AWS accounts, regions, governance, security, remediation, cost controls, approvals, and evidence from a product portal instead of scattered scripts and manual checklists.

## Where does a customer start?

Customers start at the VayuNetrix parent website:

- [www.vayunetrix.com](https://www.vayunetrix.com)

The parent website handles registration, email confirmation, product selection, quote/order/subscription state, support entry, and product launch.

## Where is the AWS Platform portal?

The AWS Platform portal is:

- [aws-platform.vayunetrix.com](https://aws-platform.vayunetrix.com)

The API is:

- [api.aws-platform.vayunetrix.com](https://api.aws-platform.vayunetrix.com)

Customers should normally reach the portal through signed handoff from the parent website.

## Is this an AWS Control Tower replacement?

No. VayuNetrix is designed to work with AWS foundation services and add a guided product layer around planning, approvals, evidence, governance, drift remediation, and cost controls.

## Why not just use Terraform directly?

Terraform is powerful, but organizations also need intake validation, approval workflows, policy checks, drift detection, remediation routing, evidence generation, and customer-friendly status views.

## Does the hosted portal store AWS credentials?

No. The intended trust model keeps credentials local to the customer-controlled connector/runtime environment.

## Does the hosted portal store Terraform state?

No. Terraform state should remain in the customer-controlled environment or approved customer state backend.

## What does the connector do?

The connector runs in the customer environment, reads local artifacts, executes approved workflows, and streams sanitized status back to the portal.

## What data does the hosted platform store?

The hosted platform stores support-safe metadata such as user/tenant references, workspace metadata, package/entitlement summaries, approval status, run summaries, and evidence/report indexes. It should not store credentials, Terraform state, tfvars bodies, ARNs, account IDs, raw logs, or private architecture details.

## Can this support existing AWS accounts?

The product vision includes both new AWS foundation creation and existing AWS estate adoption.

## What is GateForge?

GateForge is the next VayuNetrix product under development. It focuses on approved infrastructure templates, Terraform plan review, policy checks, named approval, controlled apply, and audit evidence for regulated engineering teams.

## Where is the source code?

Public-safe docs are here:

- [gprai/vayunetrix-platform-docs](https://github.com/gprai/vayunetrix-platform-docs)

Implementation repositories:

- Parent website: [gprai/vayunetrix](https://github.com/gprai/vayunetrix)
- AWS Platform implementation: [gprai/aws-platform-engineering](https://github.com/gprai/aws-platform-engineering)
- GateForge: [gprai/GateForge](https://github.com/gprai/GateForge)

## Is the product ready for broad public production use?

The platform is in beta/productization. Production readiness work continues around security proof, cost control, connector hardening, worker execution, operational runbooks, support model, legal/commercial readiness, and customer onboarding.
