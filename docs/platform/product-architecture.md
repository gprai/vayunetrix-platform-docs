# Product Architecture

The platform is organized around a hosted SaaS control plane, a secure client connector, and a client-side execution plane.

![VayuNetrix AWS Platform architecture](../../diagrams/vayunetrix-platform-architecture.png)

## Major Components

### Customer Experience

- parent website and product entry point
- signup, login, and email confirmation
- workspace home
- guided architecture builder
- package and pricing selection
- approval center
- live operations console
- governance, security, drift, remediation, cost, and evidence dashboards

### Hosted SaaS Control Plane

The hosted portal stores non-sensitive product metadata only:

- users and tenant metadata
- package selections
- approval metadata
- sanitized report indexes
- evidence indexes
- run metadata
- billing metadata

It does not store Terraform state, tfvars bodies, credentials, live AWS account inventory, ARNs, account IDs, or private architecture details.

### Secure Client Connector And Execution Plane

The connector runs in the customer-controlled environment. It is responsible for reading local customer artifacts, running approved commands, and streaming sanitized status back to the portal.

The connector boundary allows the platform to provide guided automation while keeping sensitive customer data local.

### Platform Intelligence And Orchestration

The private implementation repo contains the platform engine that supports:

- intake validation
- account planning
- Terraform orchestration
- governance and security checks
- drift detection
- remediation planning and execution gates
- cost governance
- evidence generation

### AWS Foundations And Services

The platform is designed to work with AWS services such as:

- AWS Organizations
- Control Tower
- IAM Identity Center
- GuardDuty
- Security Hub
- AWS Config
- CloudTrail
- IAM Access Analyzer
- S3 public access controls
- VPCs, networking, and future enterprise networking patterns
- StackSets, EventBridge, SSM Automation, and remediation workflows

## Main Implementation Repo

The implementation is maintained privately in:

- [gprai/aws-platform-engineering](https://github.com/gprai/aws-platform-engineering)
