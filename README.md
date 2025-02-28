# terraform-cheatsheet
 This repository is a cheatsheet for Arthur Gassmann for Terraform work. Based on KodeKloud and Terraform documentation


# Terraform commands
- The easiest Terraform Workflow:
1. Initialize Terraform Configuration file and / or download new providers ```terraform init```
2. See the Blueprint of Terraform Configuration - what is going to be changed ```terraform plan```
3. Apply the changes on the infrastructure. Confirm with 'yes' ```terraform apply```
- Apply changes and overwrite variables (highest priority for overwrite) ```terraform apply var "filename= filename=/root/pets.txt " var "content= We love Pets!Pets!" var "prefix= Mrs " var "separator= separator=.." var "length= 2```
- Also possible to set Environment Variable with Prefix 'TF_VAR_VarName' ```export TF_VAR_filename ="="/root/pets.txt```
- Validate Syntax of Terraform Configuration File. Should be done before apply! ```terraform validate```
- Display all output variables of the Terraform Configuration ```terraform output```
- Display only desired output variable of Terraform Configuration ```terraform output <variablename>```
- Format Code in HCL Canonical standard ```terraform fmt```
- Show the applied configuration from the state ```terraform state```
- Show the created resources incl. IDs ```terraform show```
- Show only the selected resources values ```terraform state show <resource>_<resource_type>.<name>```
- Show used terraform providers (plugins) ```terraform providers```
- Mirror the provider in another directory ```terraform providers mirror /other/dir/```
- Show the resource dependencies graphically ```terraform graph | dot -Tpng > graph.png``
- Taint a ressource for recreation ```terraform taint resouce_type.resource_name```
- Untaint a ressource to avoid recreation ```terraform untaint resouce_type.resource_name```
- Set LogLevel with Env Variable ```export TF_LOG=<LogLevel>```
- Define file where logs are stored with Env Variable ```export TF_LOG_PATH=/tmp/terraform.log```
- Unset Log path to destroy logs ```unset TF_LOG_PATH```
- Import unmanaged resources to terraform ```terraform import <resouce_type>.<resource_name> <attribute>```
- Create a key pair for AWS EC2 (Example): ```aws ec2 create-key-pair --endpoint http://aws:4566 --key-name jade --query 'KeyMaterial' --output text > /root/terraform-projects/project-jade/jade.pem```
- Example how Terraform State can be used in JQuery: ```terraform show -json | jq '.values.root_module.resources[] | select(.type == "aws_instance" and .name == "jade-mw")'```
- Terraform get command for Module ```terraform get```
- Use Console command to test logic of functions in tf files ```terraform console```

# Terraform documentation links
- Registry: https://registry.terraform.io/
- Providers: https://registry.terraform.io/browse/providers
- Lifecycle Meta arguments: https://developer.hashicorp.com/terraform/language/meta-arguments/lifecycle 
- Depends On Meta arguments: https://developer.hashicorp.com/terraform/language/meta-arguments/depends_on
- Count Meta argument: https://developer.hashicorp.com/terraform/language/meta-arguments/count 
- For Each argument: https://developer.hashicorp.com/terraform/language/meta-arguments/for_each 
- Datasources (used for READ data): https://developer.hashicorp.com/terraform/language/data-sources 
- AWS Provider: https://registry.terraform.io/providers/hashicorp/aws/latest/docs
- Remote State: https://developer.hashicorp.com/terraform/language/state/remote-state-data
- How to set up: https://spacelift.io/blog/terraform-remote-state 
- Taint: https://developer.hashicorp.com/terraform/cli/commands/taint 
- Provisioners (should be avoided if not needed and other methods used like aws_instance.user_data): https://developer.hashicorp.com/terraform/language/resources/provisioners/syntax
- Import unmanaged resources to terraform so that terraform manages it: https://developer.hashicorp.com/terraform/cli/import
- Modules: https://developer.hashicorp.com/terraform/language/modules
- Registry Modules: https://registry.terraform.io/browse/modules
- Test functions / logic of terraform file: https://spacelift.io/blog/terraform-console
- Terraform functions: https://spacelift.io/blog/terraform-functions-expressions-loops 
- Terraform Workspaces: https://spacelift.io/blog/terraform-workspaces

