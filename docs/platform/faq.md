# FAQ

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

## Can this support existing AWS accounts?

The product vision includes both new AWS foundation creation and existing AWS estate adoption.

## Is the product ready for public production use?

The platform is under active productization. Production go-live depends on cloud deployment, email provider, database validation, worker runtime, connector authentication, CI/CD, scans, backup/restore, and commercial readiness.

## Where is the source code?

The source code is maintained privately in [gprai/aws-platform-engineering](https://github.com/gprai/aws-platform-engineering).
