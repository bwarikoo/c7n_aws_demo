# c7n_aws_demo
This repo is for integration between Cloud Custodian &amp; AWS

## Installation
1. Install custodian by running the below command.
    `pip install c7n`
2. Configure your AWS using AWS CLI. You need to pass the ACCESS_KEY_ID and SECRET_ACCESS_KEY

## Policy ec2_startstop_policy.yml
This YAML file contains policy for starting and stopping ec2 instances having specific tag as key; value can be anything.

## How to run policy?
1. Validate the configuration file to check if the policy has been written correctly.
    `custodian validate ec2_startstop_policy.yml`
2. Dry Run the policy (no actual execution happens).
    `custodian run --dryrun ec2_startstop_policy.yml`
3. Run the config file for policies to apply to the EC2 instances.
    `custodian run --region us-east-1 --output-dir out ec2_startstop_policy.yml`