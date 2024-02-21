# Gitops approach for deployment

## Status
ACCEPTED

## Context
Application level changes should be rolled out across all environments including IOT devices faster.

## Decision
We use [ArgoCD](https://argo-cd.readthedocs.io/en/stable/) for continuous deployment following gitops approach. The ***ArgoCD*** agent running on the environment will keep polling a git repository and sync whenever the desired state changes in the git repository.

## Consequences
Faster time to market.
