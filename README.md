# terraform-cheatsheet
 This repository is a cheatsheet for Arthur Gassmann for Terraform work. Based on KodeKloud and Terraform documentation


# Terraform commands
- The easiest Terraform Workflow:
1. Initialize Terraform Configuration file and / or download new providers ```terraform init```
2. See the Blueprint of Terraform Configuration - what is going to be changed ```terraform plan```
3. Apply the changes on the infrastructure. Confirm with 'yes' ```terraform apply```
- Validate Syntax of Terraform Configuration File. Should be done before apply! ```terraform validate```
- Display all output variables of the Terraform Configuration ```terraform output```
- Display only desired output variable of Terraform Configuration ```terraform output <variablename>```
- Format Code in HCL Canonical standard ```terraform fmt```
- Show the applied configuration from the state ```terraform state```
- Show the created resources incl. IDs ```terraform show```
- Show only the selected resources values ```terraform state show <resource>_<resource_type>.<name>```
- Show used terraform providers (plugins) ```terraform providers```
- Mirror the provider in another directory ```terraform providers mirror /other/dir/```
- Show the resource dependencies graphically ```terraform graph | dot -Tpng > graph.png```


# Terraform documentation links
- Registry: https://registry.terraform.io/
- Providers: https://registry.terraform.io/browse/providers
- Terraform Lifecycle Meta arguments: https://developer.hashicorp.com/terraform/language/meta-arguments/lifecycle 
