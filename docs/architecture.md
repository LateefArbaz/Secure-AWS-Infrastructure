# Secure AWS Infrastructure — Architecture

## Purpose

This project demonstrates how to design and manage a security-focused AWS environment using Infrastructure as Code.

The environment is designed around least-privilege access, network segmentation, centralized visibility, security monitoring, and repeatable infrastructure deployment.

## Architecture Goals

The infrastructure should:

* Separate public and private network resources.
* Minimize unnecessary internet exposure.
* Apply least-privilege access controls.
* Centralize security-relevant logging.
* Provide visibility into infrastructure activity.
* Detect potentially suspicious activity.
* Be reproducible through Terraform.
* Support automated validation and security checks through CI/CD.

## Initial Architecture

The environment will contain:

* A dedicated Amazon VPC.
* Public and private subnets across multiple availability zones where practical.
* Internet Gateway for controlled public connectivity.
* NAT Gateway for required outbound connectivity from private resources.
* Route tables with explicit routing.
* Security groups following least-privilege principles.
* IAM roles and policies.
* AWS CloudTrail for API activity logging.
* Amazon CloudWatch for monitoring and observability.
* Amazon GuardDuty for managed threat detection.

## Security Principles

The architecture follows several core principles:

### Least Privilege

Users, services, and workloads should receive only the permissions required to perform their intended functions.

### Defense in Depth

Security should not depend on a single control. Network controls, identity controls, logging, monitoring, and threat detection should work together.

### Minimize Attack Surface

Resources should not be publicly accessible unless there is a clear architectural requirement.

### Visibility

Important infrastructure and security events should be logged and monitored so that suspicious activity can be investigated.

### Infrastructure as Code

Infrastructure should be defined in version-controlled Terraform configuration rather than relying on undocumented manual configuration.

## Planned Evolution

The project will be developed incrementally:

1. Network foundation
2. IAM and access controls
3. Logging and monitoring
4. Threat detection
5. Security validation
6. CI/CD automation
7. Documentation and architectural review
