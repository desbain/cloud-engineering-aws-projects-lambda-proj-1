# First Lambda Function — Packaging, IAM, and Debugging

An introductory AWS Lambda project covering the full lifecycle of deploying a Python function
from scratch: packaging code and dependencies, creating the IAM execution role, deploying,
invoking, and debugging a real runtime error.

## What was built

- A Python Lambda function, packaged with its dependencies into a deployment ZIP
- A dedicated IAM role for the function, with a trust policy scoping `AssumeRole` to the
  Lambda service, and confirmation the function assumed the role correctly
- The function deployed, invoked, and iterated on after hitting (and fixing) a runtime error
- CloudWatch Logs used throughout to inspect execution output

## Key screenshots (in order)

1. `creating packages and function for lambda.png` — packaging dependencies for the function
2. `zip file created.png`, `verify packages contents of zip file.png` — building and checking the deployment ZIP
3. `created lamdba trust policy.png`, `created lamdba IAM role.png` — IAM role + trust policy for the function
4. `lamda assumed IAM role.png`, `lambda role confirmed.png`, `confirm policy assumed by lambda.png` — verifying the execution role is attached correctly
5. `lambda function created.png`, `log-group-created.png` — function deployed, log group provisioned
6. `lambda function active.png`, `lambda function invoked.png` — first invocation
7. `lambda function response-error.png`, `used claude to decode error.png` — a runtime error surfaced on invocation, debugged with the help of Claude
8. `lambda function created- again.png`, `log-group-created.again.png` — redeploying the fixed function
9. `lambda function invoked.success.png`, `lambda function invoked.success view response code 200.png`, `lambda function response.png` — successful invocation with a 200 response
10. `log-group-check.png`, `log-group-events executed by lambda.png`, `cloud watch log-group-events executed by lambda.png` — reviewing execution logs in CloudWatch
11. `lambda project plan via claude.png`, `lambda handler explanation.png` — planning notes and handler walkthrough

## AWS services used

Lambda, IAM, CloudWatch Logs.

## Notes

This project doubles as a debugging log — the error/fix screenshots (`response-error` →
`used claude to decode error` → `created-again` → `invoked.success`) show the actual
troubleshooting loop from a failed invocation to a working one.
