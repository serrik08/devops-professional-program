# Terraform Cheatsheet

## Core workflow

```bash
terraform init          # initialize, download providers
terraform validate      # syntax check
terraform fmt           # format files
terraform plan          # preview changes
terraform apply         # apply changes
terraform destroy       # destroy all resources

# Non-interactive
terraform apply -auto-approve
terraform destroy -auto-approve

# Target specific resource
terraform plan -target=aws_instance.web
terraform apply -target=module.eks
```

## Variables

```bash
# Pass on CLI
terraform apply -var="region=us-east-1"
terraform apply -var-file="prod.tfvars"

# Environment variables
export TF_VAR_region=us-east-1
export TF_VAR_environment=dev
```

## State

```bash
terraform state list                        # list all resources
terraform state show <resource>             # show details
terraform state mv <old> <new>              # rename/move
terraform state rm <resource>               # remove from state (not destroy)
terraform import <resource> <id>            # import existing resource
```

## Workspaces

```bash
terraform workspace list
terraform workspace new dev
terraform workspace select prod
terraform workspace show
terraform workspace delete dev
```

## Output

```bash
terraform output
terraform output <name>
terraform output -json
```

## Modules

```bash
# Typical structure
module/
  main.tf
  variables.tf
  outputs.tf
  versions.tf

# Call a module
module "vpc" {
  source  = "./modules/vpc"
  cidr    = "10.2.0.0/16"
}
```

## Remote state (S3 + DynamoDB)

```hcl
terraform {
  backend "s3" {
    bucket         = "my-tfstate"
    key            = "plat/dev/terraform.tfstate"
    region         = "us-east-1"
    dynamodb_table = "tf-locks"
    encrypt        = true
  }
}
```

## AWS provider with profile

```bash
# Preferred: environment variable
export AWS_PROFILE=plat-dev
terraform plan

# Never hardcode profiles in provider.tf
```

## Useful commands

```bash
terraform graph | dot -Tpng > graph.png    # visualize dependency graph
terraform providers                         # show providers in use
terraform version                           # show version
terraform force-unlock <lock-id>            # release stuck lock
```

---
*Last updated: 2026-06 | Provider: aws ~> 5.0 | Terraform >= 1.6.0*
