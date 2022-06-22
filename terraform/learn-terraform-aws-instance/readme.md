# Terraform AWS tutorials

## Infrastructure as Code
* Terraform can manage infrastructure on multiple cloud platforms.
* The human-readable configuration language helps you write infrastructure code quickly.
* Terraform's state allows you to track resource changes throughout your deployments.
* You can commit your configurations to version control to safely collaborate on infrastructure. 

### Standardize Deployment
* Scope - Identify the infrastructure for your project.
* Author - Write the configuration for your infrastructure.
* Initialize - Install the plugins Terraform needs to manage the infrastructure.
* Plan - Preview the changes Terraform will make to match your configuration.
* Apply - Make the planned changes.

## Build Infrastructure

### Terraform Block
* Contains Terraform settings
* Can set `required_providers` and their associated `source` and `version`
* Not requried but good for versioning

### Provider Block
* Set what type of provider you want to use, `provider "aws" {}`
* Don't hard code creds in any terraform file
* Can set the `profile` value in the `provider` block or set an environment variable, `export AWS_PROFILE=<profile>` where the the corresponding profile exists in the aws credentials file

### Resources Block
* `resource` is used to define componets
* These are specific to the provider you are using such as `aws_instance` for aws
* The name of the resource follows the resource component, `resource "aws_instance" "app_name" {}`

### Init repo
* `terraform init` to download aws provider and create a lock file, `terraform.lock.hcl` so you can control when you want to update the providers used for the project

### Format and Validate Config
* `terraform fmt` to format the config
* `terraform validate` to validate the config

### Create Infrastructure
* `terraform apply` to create the infrastructure
* prints a plan and prompts for your approval to create

### Inspect State
* `terraform.tfstate` file is created after the apply
* This file should be stored remotely and only certain individuals should be given access to it
* Remote backends you can use to store and manage state
* Inspect state using `terraform show`

### Manage State
* `terraform state list`

## Change Infrastructure
* Whenever you change infrastructure you will see `+/-` when running `apply` or `plan` to show you what parts of your system are being modified

## Destory Infrastructure
* `terraform destroy` terminates all resources managed by Terraform project

## Define Input Variables
* Define variables in a file named `variables.tf` and add a `variable <variable name> {}` block
* Reference variables as `var.<variable name>`

### Variable Block
* Can have `description` of variable
* `type` of variable should be defined
* `default` can be described as a default when nothing is passed in

### Passing in variables
* Can pass in a variable to override the default using `-var <variable name>=<variable value>` flag on `terraform apply`

## Outputs
* Can define an `output <output name> {}` block
* Running `terraform apply` will show the ouput values when done
* `terraform output` can also get these outputs from a query

### Output Block
* `description` is the description of the output
* `value` is where it can pull the value from the `main.tf` to then inspect

## Store Remote State
* In production we should keep state secure and encrypted
* Run terraform in remote environment with shared access to state
* Terraform Cloud is a great place to accomplish this

### Cloud Block
* Can add a `cloud {}` block in the `terraform` block
* `organization` for the org name in `cloud` block`
* `workspaces` block in the `cloud` block which has a `name` attribute

### Terraform Login
* Run `terraform login` to login into the cloud 

### Initialize Terraform on cloud
* Run `terraform init` to get cloud environment to initialize
* Can delete the local instance of the `terraform.tfstate`

### Workspace Variables
* After `init` is run, a workspace is created
* Can set workspace variables such as env variables for aws profiles or creds

### Apply the config
* Apply the config with a `terraform apply` to apply these changes to the remote env




