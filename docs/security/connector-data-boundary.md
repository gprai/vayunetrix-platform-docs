# Connector Data Boundary

The secure local connector is central to the VayuNetrix trust model.

## Why The Connector Exists

The platform needs to help customers run Terraform, AWS CLI, policy checks, drift detection, and remediation workflows without moving sensitive customer artifacts into the hosted SaaS database.

The connector keeps sensitive execution context local.

## Local To Customer Environment

The following stay local to the customer environment:

- client AWS account IDs
- account emails from intake
- AWS profiles and credentials
- Terraform state
- generated tfvars
- live reports with ARNs
- private architecture details
- workbook contents when sensitive
- raw command logs

## Hosted Portal Receives

The hosted portal receives only sanitized data:

- run status
- current phase
- approval state
- report index
- evidence index
- high-level summaries
- selected package metadata
- connector heartbeat metadata

## Execution Safety

Connector execution should be governed by:

- signed job manifests
- command allowlists
- expiry and replay protection
- package entitlement checks
- approval binding
- policy validation before apply
- sanitized live status streaming
- cache cleanup at logout or disconnect

## Customer Benefit

The customer gets a guided portal experience without giving the SaaS database their full AWS estate details or Terraform state.
