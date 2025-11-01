# Kubernetes Manifests for ACB Project

This repository contains Kubernetes manifests for the ACB Project.

## Purpose

This is a **GitOps manifest repository** that serves as the single source of truth for Kubernetes deployments. It is:
- **Watched by ArgoCD** for automatic deployments
- **Automatically updated** by GitHub Actions from the private app repository

## Important Notes

**This repository is automatically managed by CI/CD. Manual changes are not recommended.**

All changes should come from the automated CI/CD pipeline. Manual changes will:
- Cause sync conflicts with ArgoCD
- Be overwritten by the next automated update
- Break the GitOps workflow

## Rollback

To rollback to a previous version:

### Via Git

```bash
# Find the commit with the version you want
git log --oneline

# Revert to that commit
git revert <commit-hash>
git push origin main

# ArgoCD will automatically sync the rollback
```



