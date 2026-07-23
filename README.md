# agent-workflow-counterexample

This repository is an **intentionally vulnerable demo** used to show how a
GitHub branch-protection configuration can consider an agent-authored pull
request mergeable even though its current sensitive commit was never reviewed
by a human.

## What this repository is

- A minimal mock "production" configuration (`infra/prod/network-policy.json`).
- A CI check (`validate`) that intentionally validates **syntax only**.
- A mock deployment workflow (`deploy-production`) that only echoes the policy
  file. It deploys nothing.
- An `.agentguard.yml` policy file consumed by an external verifier that
  compiles the workflow into a TLA+ model and model-checks it with TLC.

## What this repository is not

- There is **no real infrastructure** behind any file here.
- There are **no credentials, secrets, or cloud accounts** attached.
- Merging or "deploying" here has no effect outside this repository.

Do not use this configuration as a template for real projects: the branch
protection settings are deliberately misconfigured for demonstration purposes.

## Deployment

Production deployment runs automatically after changes merge into `main`.
