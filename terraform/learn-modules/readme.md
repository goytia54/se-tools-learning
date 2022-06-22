# Modules

## Problems without modules
* Understanding and navigating the configuration files will become increasingly difficult.
* Updating the configuration will become more risky, as an update to one section may cause unintended consequences to other parts of your configuration.
* There will be an increasing amount of duplication of similar blocks of configuration, for instance when configuring separate dev/staging/production environments, which will cause an increasing burden when updating those parts of your configuration.
* You may wish to share parts of your configuration between projects and teams, and will quickly find that cutting and pasting blocks of configuration between projects is error prone and hard to maintain.

## Module: Problem Solver
* Organize configuration - Modules make it easier to navigate, understand, and update your configuration by keeping related parts of your configuration together. Even moderately complex infrastructure can require hundreds or thousands of lines of configuration to implement. By using modules, you can organize your configuration into logical components.
* Encapsulate configuration - Another benefit of using modules is to encapsulate configuration into distinct logical components. Encapsulation can help prevent unintended consequences, such as a change to one part of your configuration accidentally causing changes to other infrastructure, and reduce the chances of simple errors like using the same name for two different resources.
* Re-use configuration - Writing all of your configuration from scratch can be time consuming and error prone. Using modules can save time and reduce costly errors by re-using configuration written either by yourself, other members of your team, or other Terraform practitioners who have published modules for you to use. You can also share modules that you have written with your team or the general public, giving them the benefit of your hard work.
* Provide consistency and ensure best practices - Modules also help to provide consistency in your configurations. Not only does consistency make complex configurations easier to understand, it also helps to ensure that best practices are applied across all of your configuration. For instance, cloud providers give many options for configuring object storage services, such as Amazon S3 or Google Cloud Storage buckets. There have been many high-profile security incidents involving incorrectly secured object storage, and given the number of complex configuration options involved, it's easy to accidentally misconfigure these services.

## What is a module?
* Set of config files in single directory `main.tf`, `variables.tf`, `outputs.tf`, `README.md`

### Calling Modules
* Use `module` block calls in the root `.tf` file

### Remote or Local
* Modules can be remote or local

## Module Best Practices
* Name your provider `terraform-<PROVIDER>-<NAME>`. You must follow this convention in order to publish to the Terraform Cloud or Terraform Enterprise module registries.

* Start writing your configuration with modules in mind. Even for modestly complex Terraform configurations managed by a single person, you'll find the benefits of using modules outweigh the time it takes to use them properly.

* Use local modules to organize and encapsulate your code. Even if you aren't using or publishing remote modules, organizing your configuration in terms of modules from the beginning will significantly reduce the burden of maintaining and updating your configuration as your infrastructure grows in complexity.

* Use the public Terraform Registry to find useful modules. This way you can more quickly and confidently implement your configuration by relying on the work of others to implement common infrastructure scenarios.

* Publish and share modules with your team. Most infrastructure is managed by a team of people, and modules are important way that teams can work together to create and maintain infrastructure. As mentioned earlier, you can publish modules either publicly or privately. We will see how to do this in a future tutorial in this series.

## Modules From Registry

### Terraform Block
```
terraform {
  required_providers {
    aws = {
      source = "hashicorp/aws"
    }
  }
}
```

### Module Block
```
module "vpc" {
  source  = "terraform-aws-modules/vpc/aws"
  version = "2.21.0"

  name = var.vpc_name
  cidr = var.vpc_cidr

  azs             = var.vpc_azs
  private_subnets = var.vpc_private_subnets
  public_subnets  = var.vpc_public_subnets

  enable_nat_gateway = var.vpc_enable_nat_gateway

  tags = var.vpc_tags
}
```
* `var`(s) are defined in the `variables.tf`
* The required paramters can be found on the terraform documentation for the said module

### Root Variables
* Root variables can be defined in the `variables.tf` file

### Output variables
* Can reference variables using `module.<module type>.<variable name>` for `output` blocks, found in `output


## Local Modules
* Create a directory called `modules` and then you can create more directories for the given modules within this parent module folder.
* Individual module directories then have `main.tf`, `variables.tf`, `outputs.tf` `LICENSES` `README.md` files

### Install the local module
* `terraform get` or `terraform init` to install the modules

### Reference local moduels
* Can reference local modules in `module` block via the `source` parameter `source = ./modules/<module-dir>`

## [Module Create - Recommended Pattern](https://learn.hashicorp.com/tutorials/terraform/pattern-module-creation?in=terraform/modules)
