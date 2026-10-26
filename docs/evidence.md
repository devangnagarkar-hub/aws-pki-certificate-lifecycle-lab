# Evidence Index

All screenshots are from a personal AWS lab.
Account-specific details are redacted where appropriate.

## 1. Private S3 bucket for CRLs
![Private CRL bucket](../Screenshots/01-s3-crl-bucket.png)

## 2. Private CA configuration
![Private CA configuration](../Screenshots/02-private-ca-created.png)

## 3. Root CA active
![Root CA active](../Screenshots/03-root-ca-active.png)

## 4. ACM private certificate issued
![Private certificate issued](../Screenshots/04-acm-private-certificate-issued.png)

## 5. SNS topic and subscription
![SNS configuration](../Screenshots/05-sns-certificate-alert-topic.png)

## 6. Lambda execution
![Lambda execution](../Screenshots/06-lambda-certificate-monitor-success.png)

## 7. IAM permissions
![IAM policy](../Screenshots/07-lambda-least-privilege-policy.png)

## 8. Daily schedule
![Daily schedule](../Screenshots/08-eventbridge-daily-schedule.png)

## 9. KMS signature verification
![KMS verification](../screenshots/09-kms-signature-verified.png)

## 10. CloudTrail audit events
![CloudTrail audit events](../screenshots/10-cloudtrail-pki-audit-events.png)
