# Terraform
* Notes from LinkedIn course "Learning Terraform"

## Infrastructure as Code
* Terraform figures out resource ordering
* Compiles the plan and see if you want it to happen
* Compares the code to the state and writes a plan
* What needs to be done and in what order
* Uses a graph to decide to do this, directed(ordered), acyclic(no cycles)

### `plan` and `apply`
`terraform plan -destory -out=example.plan`
* `destory` will show the plan to destroy and recreate the plan
* `out` will save the plan to use with destory
`terraform show example.plan`
* will show the plan
`terraform apply example.plan`
* will run the plan

### Terraform State
* Reality of the infrastructure
* State of the State, state file
* Remote storage of state, delegate and read access
* `terraform state list` cmd, should not be done lightly 
* `terraform state show <resource>`
* `terraform show` gives every resource
* `terraform show -json` to give every resource in json

### Terraform Graph
* `terraform graph`
* Use `webgraphviz.com` to visualize

### Terraform Apply
* Can split plan and apply

## Resources
* The what of the infrastructure
* Must have `provider` defined for the kind of provider

### Define resources
* `resource "aws_s3_bucket" "tf" {}`
* Resources have arguments

### Basic resources
* `resource <resource> <resource name>`
* s3 buckets
* vpc, virtual private cloud
* aws_security_group, firewalls
* aws_instance, ec2 server
* aws_eip, static public ip address
 
## Style
* two spaces for tabs
* meta arguments, some have block format
* single arguments should be seperated from meta, single spaced blank lines
* line up equal signs

### Files
* Naming files `<component>-<env>-<region>-<whatever makes sense>`

### Scaling
* Can de-couple id addresses
* Can scale instances

### Follow ups
* Investigate `jq` command line tool

## Load Balancing
* Can use asg and elb and don't just use manual instances

## Variables
* Can define variables on top of the file
* `variable "whitelist" { type = list(string)}` and reference as `var.whitelist`

### Data Sources
* Use aws as the data sources
* Can use `aws_ami` to track based on owners and tags
* Track the `ami` versions better
* filter block

## Modules
* Bundle together a subset of code
* Pass in arguments
* Needs
  * needs a main.tf
  * variables.tf
  * outputs.tf
  * README.ME
* Can use s3 for modules
* Versioning available
* Module registry, publish their own modules

### Talking to Modules
* tell terraform wher to find module
* pass in two arguments

