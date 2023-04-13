# Waypoint Project Template Example

This is an example of how to create and use project templating in HCP Waypoint.

Pre-Requisites

AWS Account with Admin Permissions

## Initial Setup

### Terraform Module Creation

#### Publish A Module
This should be already done. There should be a no-code module in hcp_waypoint_integration Terraform organization
called `example-microservice-ecs-allenvs`

### Terraform Cloud Workspaces

1. Create terraform cloud workspaces in the TFC User Interface based on the following terraform configurations provided in this example:
        `terraform-aws-example-microservice-infra`
        `terraform-aws-example-network`
2. Go to Settings for the created TFC workspaces, Under `Remote State Sharing` allow `Share with all workspaces in this organization`.

2. Create a global variable set for your AWS Credentials.
   (To export your AWS credentials via doormat, please run the following command: `doormat aws tf-push variable-set --account your_sandbox_aws_account_number --id some_varset_id`)

### AWS Steps with Terraform

Create the baseline infrastructure with the following steps.

1. Navigate to the `terraform-aws-example-network` directory found in this example and run `terraform init` and the `terraform apply` command.
   (If you are prompted for AWS Credentials, `eval $(doormat aws export --account your_sandbox_aws_account_number)` to export your aws creds
    into your local environment)

2. Navigate to the `terraform-aws-example-microservice-infra` directory found in this example and run `terraform init` and the  `terraform apply` command.


## Waypoint Template Steps 

