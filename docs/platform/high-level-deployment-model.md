# High-Level Deployment Model

The platform is planned as a hosted SaaS control plane plus a customer-side connector.

## Hosted Components

- customer portal frontend
- portal backend API
- metadata database, expected to be PostgreSQL for hosted environments
- queue or workflow engine
- worker pool
- secret manager
- email provider
- payment provider integration
- observability stack
- sanitized evidence/report metadata storage

## Customer-Side Components

- secure local connector
- local artifact workspace
- private runtime cache
- AWS CLI and Terraform runtime
- customer AWS credentials/profile context

## Deployment Environments

A production rollout should include:

- development
- staging
- production
- backup and restore validation environment

## Infrastructure Concerns

Before public production launch, the platform needs:

- cloud provider decision
- production PostgreSQL validation
- email provider provisioning
- payment provider provisioning
- CI/CD pipeline
- container registry
- external queue/broker
- observability
- backup and disaster recovery
- security scan gates

The implementation roadmap is tracked privately in the main code repository and publicly summarized in this docs repository.
