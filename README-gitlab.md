# GitLab CI/CD Workflow for Runtime Action Deploy

This GitLab CI/CD workflow runs the Runtime Action Deploy with the specified parameters.

## Inputs

The following environment variables must be configured in your GitLab CI/CD settings:

- `FEATURES_LEVEL_LOG`: Log Level (required)
- `CLIENT_ID`: CLIENT ID (required)
- `CLIENT_KEY`: CLIENT KEY (required)
- `CLIENT_REALM`: CLIENT REALM (required)
- `REPOSITORY_NAME`: Git Repository Name (required)
- `AWS_ACCESS_KEY_ID`: AWS ACCESS KEY ID from console (optional)
- `AWS_SECRET_ACCESS_KEY`: AWS SECRET ACCESS KEY from console (optional)
- `AWS_SESSION_TOKEN`: AWS SESSION TOKEN from console (optional)
- `AWS_REGION`: AWS REGION (required)
- `AWS_ROLE_ARN`: AWS ROLE ARN (optional)
- `RUN_TASK_ID`: Runtime Run Task Id (required)
- `CONTAINER_URL`: Deploy Container URL (optional, default: `stackspot/runtime-job-deploy:latest`)
- `FEATURES_TERRAFORM_MODULES`: Terraform Modules (optional)
- `PATH_TO_MOUNT`: Path to mount inside the docker (optional, default: `$CI_PROJECT_DIR`)
- `OUTPUT_FILE`: File name to save outputs (optional, default: `outputs.json`)
- `LOCALEXEC_ENABLED`: If Runtimes will allow execution of the local-exec command within terraform (optional, default: `false`)
- `TF_LOG_PROVIDER`: Level tf log provider - info, debug, warn or trace (optional)
- `CHECKOUT_BRANCH`: Whether or not checkout is enabled (optional, default: `false`)

## Usage

To use this workflow, add the above environment variables to your GitLab CI/CD settings and include the `.gitlab-ci.yml` file in your repository.

```yaml
include:
  - local: '.gitlab-ci.yml'