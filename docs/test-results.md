# Test Results

Replace "Not recorded" only after checking the actual evidence.
Do not mark an unperformed test as passed.

| Test | Expected result | Actual result | Evidence |
|---|---|---|---|
| Root CA activation | CA status Active | Not recorded | Screenshot 03 |
| Private certificate issuance | Certificate status Issued | Not recorded | Screenshot 04 |
| Lambda normal test | Inventory returned without error | Not recorded | Screenshot 06 |
| SNS test notification | Labelled test email received | Not recorded | Add email screenshot |
| Scheduler execution | New Lambda execution without manual invocation | Not recorded | Add CloudWatch screenshot |
| KMS verification | SignatureValid: true | Not recorded | Screenshot 09 |
| Modified-message test | Original signature rejected | Not recorded | Optional screenshot |
| CloudTrail event review | Relevant ACM/KMS events visible | Not recorded | Screenshot 10 |
| CloudTrail S3 delivery | Log archive delivered to bucket | Not recorded | Add S3 screenshot |

## Testing notes

- A successful manual Lambda test does not prove Scheduler invoked it.
- A test email does not prove an actual expiry condition occurred.
- An event in Event history does not by itself prove trail delivery to S3.
- Record the execution time and test date when available.
