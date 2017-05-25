# ECS with ALB example

This example shows how to launch an ECS service fronted with Application Load Balancer.

The example uses latest CoreOS Stable AMIs.

Download and install [Terraform](https://www.terraform.io/downloads.html) based on your OS.

To run, configure your AWS provider as described in https://www.terraform.io/docs/providers/aws/index.html

You'll need to have an AWS Account and a [Key-Pair](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html) for creating the infrastructure. Export the AWS Credentials on your terminal as indicated below:

```
$ export AWS_ACCESS_KEY_ID="anaccesskey"
$ export AWS_SECRET_ACCESS_KEY="asecretkey"
$ export AWS_DEFAULT_REGION="us-west-2"
```

## Get up and running

Planning phase

```
terraform plan \
	-var admin_cidr_ingress='"{your_ip_address}/32"' \
	-var key_name={your_key_name}
```

Apply phase

```
terraform apply \
	-var admin_cidr_ingress='"{your_ip_address}/32"' \
	-var key_name={your_key_name}
```

Once the stack is created, wait for a few minutes and test the stack by launching a browser with the ALB url.

## Destroy :boom:

```
terraform destroy
```
