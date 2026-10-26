# Test Results

| Test | Expected result | Actual result | Evidence |
|---|---|---|---|
| Root CA activation | CA status Active | recorded | Screenshot 03 |
| Private certificate issuance | Certificate status Issued | recorded | Screenshot 04 |
| Lambda normal test | Inventory returned without error | recorded | Screenshot 06 |
| SNS test notification | Labelled test email received | recorded | Screenshot 11 |
| Scheduler execution | New Lambda execution without manual invocation | recorded | Screenshot 12 |
| KMS verification | SignatureValid: true | recorded | Screenshot 09 |
| CloudTrail event review | Relevant ACM/KMS events visible | recorded | Screenshot 10 |

## Testing notes

- A successful manual Lambda test does not prove Scheduler invoked it.
- A test email does not prove an actual expiry condition occurred.
- An event in Event history does not by itself prove trail delivery to S3.
- Record the execution time and test date when available.
