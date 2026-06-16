# VayuNetrix AWS Platform

VayuNetrix AWS Platform is a guided AWS platform engineering product for organizations that want to create, govern, secure, operate, remediate, and evidence their AWS environment with strong approval gates.

This public repository contains business and technical overview documentation only. The private implementation and source-code repository is:

- Main implementation repo: [gprai/aws-platform-engineering](https://github.com/gprai/aws-platform-engineering)

The implementation repo is private because it contains product source code, Terraform, Python automation, portal backend/frontend, connector logic, policy packs, and internal execution workflows.

## What The Platform Does

VayuNetrix helps customers move from cloud setup uncertainty to a governed AWS operating model:

- guided architecture selection
- package and service selection
- intake validation
- account and landing-zone planning
- Terraform plan/apply approval gates
- governance and security assessment
- drift detection and remediation workflows
- cost governance, showback, and chargeback reporting
- evidence packs for audit and review

## Architecture

![VayuNetrix AWS Platform architecture](diagrams/vayunetrix-platform-architecture.png)

Customer workflow view:

![VayuNetrix customer workflow](diagrams/vayunetrix-customer-workflow.svg)

## Public Documentation

- [Business overview](docs/platform/business-overview.md)
- [Product architecture](docs/platform/product-architecture.md)
- [Customer journey](docs/platform/customer-journey.md)
- [Service packages](docs/platform/service-packages.md)
- [Security and trust model](docs/security/security-and-trust-model.md)
- [Connector data boundary](docs/security/connector-data-boundary.md)
- [High-level deployment model](docs/platform/high-level-deployment-model.md)
- [Public roadmap](docs/roadmap/public-roadmap.md)
- [FAQ](docs/platform/faq.md)
- [Parent website content](docs/website/parent-website-content.md)
- [Public onboarding guide](docs/onboarding/public-onboarding-guide.md)

## Repository Boundary

This public repository does not contain:

- Terraform implementation code
- Python platform engine code
- portal API or frontend source code
- connector source code
- policy source code
- generated tfvars
- Terraform state
- live AWS reports
- customer account IDs, ARNs, credentials, emails, or private architecture details

## Product Status

The platform is under active productization. Current focus areas include production readiness, public documentation, cloud deployment planning, connector trust model, commercial packaging, and customer onboarding material.
