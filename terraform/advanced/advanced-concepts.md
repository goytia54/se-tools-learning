# Advanced Concepts

## Input Varaibles
1. Default Value
2. Env variable
3. File (terraform.tfvars)
4. Command line

## Variable Types
* String
* Boolean
* Number
* List `type = list(string)` number based index
* Set 
* Map `type = map(string)` string based index 
* Object `type = object({att1=string,att2=bool})`
* Tuple

## Setting Variable Values
* Files: `terraform.tfvars` `terraform.tfvars.json`, `*.auto.tfvars` (collaborate on config)
* Env variables export `TF_VAR_key="key"`
* Command line `terraform plan -var variable=value`

### Precedent
* `Env` -> `tfvars` -> `tfvars.json` `*.auto.tfvars` -> `-var`

## Terraform Output Variables
Define as
```terraform
output "name" {
  value = aws_instance.aws_access_key
}
```

## HCL Expressions
* Predefined functions

### Terraform REPL
* `terraform console`
* can user turnary operator

### Terraform Functions
* String `split()` `join()` `length`

### `count` and `for_each` meta arguments

#### `count`
* Use `count` to create multiple times
* Output variable have to be accounted for, using `.*`, splat expression

#### `for_each`
* Iterate over sets and maps

