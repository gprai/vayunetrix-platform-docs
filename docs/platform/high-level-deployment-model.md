# High-Level Deployment Model

The VayuNetrix product family uses a shared parent website plus product-specific portals.

## Current Public Surfaces

| Surface | Purpose | URL |
| --- | --- | --- |
| Parent website | public site, registration, product selection, command center, support entry, product launch | [www.vayunetrix.com](https://www.vayunetrix.com) |
| AWS Platform portal | product workspace for AWS Platform Engineering | [aws-platform.vayunetrix.com](https://aws-platform.vayunetrix.com) |
| AWS Platform API | product API for portal and handoff workflows | [api.aws-platform.vayunetrix.com](https://api.aws-platform.vayunetrix.com) |

## Hosted Components

- parent website frontend
- parent website API
- AWS Platform portal frontend
- AWS Platform API
- metadata database, PostgreSQL for hosted environments
- queue or workflow engine
- worker pool
- AWS Secrets Manager
- SES email capability
- payment provider integration when commercial payment goes live
- observability through logs, metrics, alarms, dashboards, and issue runbooks
- sanitized evidence/report metadata storage

## Customer-Side Components

- secure local connector
- local artifact workspace
- private runtime cache
- AWS CLI and Terraform runtime
- customer AWS credentials/profile context
- customer-controlled Terraform state and generated tfvars

## Shared Infrastructure Direction

For beta and early production, the parent website and AWS Platform portal can share selected AWS infrastructure to reduce cost and simplify operations:

- shared AWS account/environment
- shared VPC and subnets
- shared ECS cluster
- shared API load balancer patterns
- shared RDS PostgreSQL with separated schemas
- shared Secrets Manager conventions
- shared CloudWatch/alerting practices

The products still need strict logical separation by schema, service, secret scope, route, and entitlement boundary.

## Deployment Environments

A mature rollout should include:

- local development
- beta
- staging
- production
- backup and restore validation environment

## Infrastructure Concerns Before Broad Production

Before public production launch, the platform needs continued hardening around:

- production PostgreSQL validation
- email and MFA flows
- payment provider live integration
- CI/CD pipeline with scans and deployment gates
- external queue/broker
- worker and connector authentication
- backup and disaster recovery
- cost control
- security scan gates
- incident response and support processes

The private implementation roadmap is tracked in the main code repositories and publicly summarized in this docs repository.
