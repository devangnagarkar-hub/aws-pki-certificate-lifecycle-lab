# aws-pki-certificate-lifecycle-lab
Personal AWS PKI lab demonstrating private certificate issuance, expiry monitoring, scheduled alerts, KMS digital signing, and CloudTrail auditing.

# AWS Cloud PKI & Certificate Lifecycle Automation Lab

## Overview

A personal AWS lab built to extend my enterprise PKI and certificate
lifecycle experience into AWS-native security operations.

The lab covers private certificate issuance, certificate inventory,
expiry monitoring, scheduled execution, email notifications,
digital signing, and audit logging.

This project uses fictional test names and contains no employer or
client data.

## Architecture

```text
AWS Private CA ----> ACM private certificate
       |
       +----------> S3 CRL storage

EventBridge Scheduler ----> Lambda certificate monitor
                                  |
                                  +----> ACM inventory and expiry checks
                                  +----> SNS email alerts
                                  +----> CloudWatch execution logs

AWS CLI ----> KMS signing and verification

CloudTrail ----> S3 audit-log storage
```

## Services used

- AWS Private CA
- AWS Certificate Manager
- Amazon S3
- AWS Lambda and Python
- Amazon SNS
- Amazon EventBridge Scheduler
- AWS IAM
- AWS KMS
- AWS CloudTrail
- Amazon CloudWatch Logs

## Lab configuration

- Region: ap-south-1
- Test certificate hostname: pki-lab.internal
- Lambda function: certificate-expiry-monitor
- Schedule: rate(1 day)
- Expiry alert threshold: 30 days
- KMS key: RSA_2048, SIGN_VERIFY
- Signing algorithm: RSASSA_PKCS1_V1_5_SHA_256

## Implementation

1. Created a private S3 bucket for CRL storage.
2. Created and activated an AWS Private CA root certificate authority.
3. Requested an ACM private certificate for a fictional internal hostname.
4. Built a Python Lambda function to inventory certificates and check expiry.
5. Granted the Lambda role ACM read and scoped SNS publish permissions.
6. Configured SNS email notifications.
7. Configured EventBridge Scheduler to invoke the monitor daily.
8. Tested KMS digital signing and signature verification.
9. Configured CloudTrail management-event delivery to S3.

Only successfully completed steps are claimed as implemented.

## Validation

See [test results](docs/test-results.md) for the recorded outcomes.

See the [evidence index](docs/evidence.md) for screenshots.

## Repository contents

- `lambda/`: certificate-monitor source code
- `policies/`: sanitized IAM policy template
- `docs/`: evidence index and test results
- `screenshots/`: redacted implementation evidence

## Relationship to my professional experience

My enterprise PKI experience includes certificate lifecycle operations,
expiry monitoring, renewal coordination, TLS troubleshooting, and incident
handling.

This personal lab demonstrates how those principles map to AWS-native
services. It is not an employer production deployment.

## Limitations

- This is a lab, not a production PKI architecture.
- A single root CA is used for simplicity.
- No production Venafi or CyberArk integration is claimed.
- Certificate issuance is demonstrated; an actual renewal is not claimed
  unless separately tested.
- A test notification verifies email delivery, not an actual expiry incident.
- Private CRL storage alone does not demonstrate client-side CRL retrieval
  or revocation enforcement.
- KMS message signing is separate from CA certificate signing.
- No infrastructure-as-code implementation is claimed.

## Cost and cleanup

AWS Private CA can incur significant recurring charges.
Resources are deleted after validation and evidence collection.

Cleanup status: UPDATE AFTER CHECKING.
