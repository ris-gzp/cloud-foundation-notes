# Why We Never Commit Secrets

## The Problem
Once a secret is committed to Git, it is FOREVER in history.
Even if you delete the file, git log still has it.
Attackers scan GitHub for exposed AWS keys 24/7.

## What Never Goes in Git
- .env files
- *.pem key files
- ~/.aws/credentials
- *.tfstate files
- Any API keys or passwords

## Solution
- Use .gitignore for sensitive files
- Use git-secrets to block accidental commits
- Use AWS Secrets Manager for runtime secrets
- Use IAM roles instead of access keys where possible
