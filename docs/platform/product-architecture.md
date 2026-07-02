# Product Architecture

The platform is organized around a parent website, a product-specific AWS Platform portal, a hosted metadata control plane, and a customer-controlled connector/runtime boundary.

![VayuNetrix AWS Platform architecture](../../diagrams/vayunetrix-platform-architecture.png)

## Business Architecture In Plain Language

The parent website is the commercial front door. It knows who the customer is, which product they selected, what package they chose, and whether the subscription is active.

The AWS Platform portal is the product workspace. It shows the customer what they can do with their selected package and routes platform actions through approvals, policy checks, and guarded execution.

The connector/runtime boundary is where sensitive customer work happens. Terraform state, generated tfvars, AWS credentials, account identifiers, ARNs, private architecture details, and raw logs stay out of the hosted product database.

## Major Components

### 1. Parent Website And Product Hub

- Public URL: [www.vayunetrix.com](https://www.vayunetrix.com)
- Repository: [gprai/vayunetrix](https://github.com/gprai/vayunetrix)

Responsibilities:

- public website and product pages
- customer registration and email confirmation
- product/package selection
- quote, order, subscription, and entitlement state
- customer command center
- support entry
- signed product launch into product portals

### 2. AWS Platform Portal

- Portal URL: [aws-platform.vayunetrix.com](https://aws-platform.vayunetrix.com)
- API URL: [api.aws-platform.vayunetrix.com](https://api.aws-platform.vayunetrix.com)
- Private implementation repo: [gprai/aws-platform-engineering](https://github.com/gprai/aws-platform-engineering)

Responsibilities:

- Workspace Home after parent handoff
- entitlement-aware navigation and feature access
- guided architecture and intake experience
- workbook upload/intake validation paths
- approval center and change preview
- live operations console
- governance, security, drift, remediation, cost, and evidence dashboards

### 3. Hosted SaaS Control Plane

The hosted control plane stores non-sensitive metadata only:

- user and tenant metadata
- package and entitlement summaries
- workspace metadata
- approval metadata
- sanitized run summaries
- sanitized report indexes
- evidence indexes
- support-safe billing/subscription references

It does not store Terraform state, tfvars bodies, credentials, live AWS account inventory, ARNs, account IDs, raw command logs, or private architecture details.

### 4. Secure Client Connector And Execution Plane

The connector runs in the customer-controlled environment. It is responsible for reading local customer artifacts, running approved commands, and streaming sanitized status back to the portal.

The connector boundary allows VayuNetrix to provide guided automation while keeping sensitive customer data local.

### 5. Platform Intelligence And Orchestration

The private implementation repo contains the platform engine that supports:

- intake validation
- account planning
- Terraform orchestration
- policy validation
- governance and security checks
- drift detection
- remediation planning and execution gates
- cost governance
- evidence generation

### 6. AWS Foundations And Services

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
- VPCs and enterprise networking patterns
- StackSets, EventBridge, SSM Automation, and remediation workflows

## Technology Flavor

Public-safe implementation highlights:

| Layer | Technology direction |
| --- | --- |
| Parent website | Next.js / React and backend API services |
| AWS Platform frontend | React/Vite portal |
| Backend APIs | Python/FastAPI-style services |
| Metadata database | PostgreSQL with product schemas |
| Hosted AWS infrastructure | ECS/Fargate, ALB, CloudFront/S3, RDS, SQS, Secrets Manager, SES, CloudWatch, WAF, Route 53/ACM |
| Infrastructure automation | Terraform |
| Platform automation | Python CLI workflows |
| Policy | OPA/Conftest-style checks |
| Evidence | sanitized report and evidence indexes |

## Related Projects

GateForge is the next VayuNetrix product under development. It follows the same product-family pattern: parent website for commercial entry, product-specific portal for execution, and strong approval/evidence boundaries.
