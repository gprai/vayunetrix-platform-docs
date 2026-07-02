# Public Roadmap

This roadmap is intentionally high level. It avoids exposing internal implementation details from private source repositories.

## Current Focus

- parent website and product hub beta testing
- AWS Platform portal beta testing
- signed handoff from parent website to AWS Platform portal
- entitlement-aware portal access
- production readiness and cost control
- public documentation refresh
- security and trust model hardening
- customer onboarding flow
- connector and worker hardening

## Near-Term Goals

- finish parent-owned commercial flow for product selection, quote, order, subscription, and entitlement state
- complete AWS Platform entitlement enforcement across UI, API, worker, connector, Terraform, remediation, and cost/governance/security views
- improve customer-facing portal UX and live operations experience
- strengthen email, MFA, support, and admin operations
- continue beta infrastructure cost optimization without breaking shared parent/product workflows
- add stronger security proof: tenant isolation tests, sensitive-data rejection tests, connector manifest tampering tests, UI XSS checks, and dependency/container scans

## Product Expansion Goals

- deeper governance reporting
- deeper security posture analytics
- drift and remediation subscription product
- enterprise cost governance and showback
- support/ticketing workflow integration
- enterprise SSO
- customer success and migration playbooks
- stronger evidence integrity and audit readiness

## Next Product: GateForge

GateForge is under development as the next VayuNetrix product.

GateForge is a controlled infrastructure delivery portal for regulated teams. A developer chooses a pre-approved infrastructure template, fills out a structured request form, receives a Terraform plan and plain-English summary, routes the change through a named approval gate, and deploys only after approval. Evidence is generated for audit and compliance review.

Planned public launch path:

- [www.vayunetrix.com/GateForge](https://www.vayunetrix.com/GateForge)

Related repo:

- [gprai/GateForge](https://github.com/gprai/GateForge)

## Long-Term Vision

VayuNetrix aims to become a family of guided cloud and AI engineering products that help customers safely request, approve, deploy, govern, remediate, and evidence cloud platforms from one customer-friendly product surface.
