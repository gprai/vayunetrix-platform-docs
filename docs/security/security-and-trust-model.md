# Security And Trust Model

The platform is designed around a clear separation between hosted product metadata and sensitive client-controlled artifacts.

## Core Security Principles

- Store only non-sensitive metadata in the hosted portal.
- Keep Terraform state, generated tfvars, credentials, account IDs, ARNs, and private architecture details local to the client workspace.
- Require approvals before high-impact changes.
- Use signed job manifests for connector execution.
- Route operations through allowlisted workflows.
- Produce sanitized evidence instead of exposing raw command output.

## Hosted Portal Data

The hosted portal may store:

- user and tenant metadata
- selected package metadata
- workspace metadata
- approval state
- sanitized run summaries
- sanitized report indexes
- evidence indexes
- billing metadata

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

The product roadmap includes:

- email confirmation
- session expiry
- password reset
- MFA using email OTP and authenticator apps
- tenant isolation
- role-based access controls
- support access approval workflows

## Connector Trust Model

The connector is the client-side component that performs local or AWS-facing execution. The hosted portal approves and signs work; the connector verifies and executes only allowlisted, signed, current requests.

## Evidence Model

Evidence is designed to be useful without leaking customer secrets:

- report status
- timestamps
- approver metadata
- high-level summaries
- pass/warn/fail counts
- sanitized findings

## Main Implementation Repo

The private implementation repo is:

- [gprai/aws-platform-engineering](https://github.com/gprai/aws-platform-engineering)
