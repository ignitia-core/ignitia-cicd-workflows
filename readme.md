# Ignitia CI/CD Workflows

This repository contains reusable GitHub Actions workflows for deploying Ignitia applications.

## Workflow Architecture

The CI/CD workflows are organized into two layers:

### 1. Bootstrap Layer

Bootstrap workflows are designed for initial deployments and environments where the Ignitia platform is not yet available. These workflows handle direct infrastructure updates without platform dependencies.

**Current Bootstrap Workflows:**
- `sync-environment.yml` - Full environment sync using platform CLI (API + UI deployment)
- `sync-environment-oidc.yml` - Simplified API-only deployment using OIDC authentication

**Use Cases:**
- Initial project setup
- Direct AWS Lambda and S3 deployments
- Environments without platform infrastructure

### 2. Platform Workflows (Future)

Platform workflows will leverage the existing Ignitia platform infrastructure to manage deployments. Instead of directly pushing to AWS, these workflows will trigger platform-managed updates via GitHub workflows.

**Planned Features:**
- Platform-native version management
- Centralized deployment orchestration
- Enhanced deployment tracking and rollback capabilities

## Migration Path

Projects should start with bootstrap workflows for initial setup. Once the platform infrastructure is established, they can migrate to platform workflows for ongoing deployments.
