# Security And Trust Model

The platform is designed around a clear separation between hosted product metadata and sensitive client-controlled artifacts.

## Core Security Principles

- Parent website owns customer identity, product selection, quote/order/subscription state, and launch handoff.
- AWS Platform portal owns product workspace, entitlement-aware views, approvals, and product operations.
- Store only non-sensitive metadata in hosted databases.
- Keep Terraform state, generated tfvars, credentials, account IDs, ARNs, raw logs, and private architecture details local to the client workspace or approved customer-controlled backend.
- Require approvals before high-impact changes.
- Use signed handoff and signed job-manifest patterns for sensitive workflow boundaries.
- Route operations through allowlisted workflows.
- Produce sanitized evidence instead of exposing raw command output.

## Hosted Portal Data

The hosted portal may store:

- user and tenant metadata
- parent product/subscription references
- selected package and entitlement summaries
- workspace metadata
- approval state
- sanitized run summaries
- sanitized report indexes
- evidence indexes
- support-safe billing metadata

## Sensitive Data Boundary

The hosted portal must not store:

- AWS access keys or session tokens
- Terraform state
- generated tfvars bodies
- account IDs
- ARNs
- raw AWS inventory
- full command logs
- private architecture details
- customer CID details

## Authentication And Authorization

The current product direction is parent-owned customer authentication:

- customer registration starts at [www.vayunetrix.com](https://www.vayunetrix.com)
- email confirmation happens through the parent website
- product access is granted through signed handoff and entitlement metadata
- AWS Platform portal consumes support-safe entitlement summaries
- operator/break-glass access remains separate from normal customer login

Roadmap hardening includes:

- MFA using email OTP and authenticator apps
- stronger RBAC by owner, approver, operator, support, billing, and auditor roles
- tenant isolation tests
- support access approval workflows
- security scans and sensitive-data rejection tests

## Connector Trust Model

The connector is the client-side component that performs local or AWS-facing execution. The hosted portal approves and signs work; the connector verifies and executes only allowlisted, signed, current requests.

The connector boundary is central to the business model: VayuNetrix guides the work, but sensitive client artifacts stay under customer control.

## Evidence Model

Evidence is designed to be useful without leaking customer secrets:

- report status
- timestamps
- approver metadata
- high-level summaries
- pass/warn/fail counts
- sanitized findings
- evidence indexes rather than raw customer files

## Related Repositories

- Public docs: [gprai/vayunetrix-platform-docs](https://github.com/gprai/vayunetrix-platform-docs)
- Parent website: [gprai/vayunetrix](https://github.com/gprai/vayunetrix)
- AWS Platform implementation: [gprai/aws-platform-engineering](https://github.com/gprai/aws-platform-engineering)
