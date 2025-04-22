# terraform-aws-infra-pipeline
Using terraform to create infra on AWS (free tier, because I ain't got no money,lol), I will use webhook to trigger the build in Jenkins

Main objective for this repo/project is to :

a) Use Terraform instead of AWS-CDK, since Terraform is provider-agnostic

b) Use S3 and DynamoDB to save Terrform state and avoid clashes if two people dediced to run "terraform apply" aka prevent state conflicts

c) IaC to scale my infrastructure and just changing Terraform files to enhance it, and Jenkins to do the rest aka CI/CD.

d) Showcase hands-on SRE skills for future employers — give them proof that I might know a thing or two :) (I have performance anxiety but who doesn't hehe)


# Project Plan 
1. Create Terraform project, it will have :
   - S3 Bucket (for state)
   - DynamoDB Table (for lock)
   - EC2 (Free Tier)
   - Load Balancers (NLB/ALB)

2. Jenkins Pipeline :
   - Triggered via GitHub webhook
   - Runs `terraform init`, `plan`, and `apply`
