# .github Repository

This repository serves as a centralized location for reusable GitHub workflow modules and Renovate bot configuration modules that are shared across multiple repositories in the organization.

## Purpose

Instead of duplicating workflow and configuration code across all repositories, this `.github` repository provides:

- **Reusable Workflow Modules**: Shared GitHub Actions workflows that can be called from other repositories
- **Renovate Bot Configuration Modules**: Centralized Renovate configurations that other repositories can extend or reference

## Benefits

- **Single Source of Truth**: Maintain workflows and configurations in one place
- **Consistency**: Ensure all repositories follow the same standards and practices
- **Easy Maintenance**: Update workflows and configurations once, apply everywhere
- **Reduced Duplication**: Avoid copying the same code across multiple repositories

## Contents

### Renovate Modules

- `renovate-module-backend.json` - Renovate configuration for backend projects
- `renovate-module-terraform.json` - Renovate configuration for Terraform projects

## Usage

### Using Renovate Modules

Other repositories can reference these Renovate modules in their `renovate.json` configuration:

```json
{
  "extends": [
    "github>traent/.github:renovate-module-backend"
  ]
}
```

### Using Reusable Workflows

Repositories can call reusable workflows from this repository in their workflow files:

```yaml
jobs:
  call-workflow:
    uses: traent/.github/.github/workflows/workflow-name.yml@master
```

## Contributing

When adding new modules or workflows to this repository, ensure they are:
- Well-documented
- Generic enough to be reused across multiple projects
- Following organization best practices
