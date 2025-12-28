## This is a simple Terraform modules repo

## To Use ec2 modules

# EC2 Terraform Module

Creates a single AWS EC2 instance.

## Usage

```hcl
module "ec2" {
  source = "git::https://github.com/arunprakash432/terraform-modules.git//ec2"

  name                = "app-server"
  ami_id              = "ami-0c02fb55956c7d316"
  instance_type       = "t3.micro"
  subnet_id           = "subnet-123456"
  security_group_ids  = ["sg-123456"]
  key_name            = "my-key"

  tags = {
    Environment = "dev"
    Terraform   = "true"
  }
}

---