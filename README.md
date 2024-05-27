steps: to create an Aws_Ec2 by Terrafrom is:
install Terraform in linux
step2: check the version of your terrafrom 
Step: install aws configure here 
it will ask the details like acces key,screat key,region,outputformat give allof those

step::now you should have your own ami id which will be there in any one of your instance in th region so 

create a file in the folder like terrafrom 
use touch command to create 
to write inside the file so use vi filenemae.tf

**use this code**

terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 4.16"
    }
  }

  required_version = ">= 1.2.0"
}

provider "aws" {
  region  = "us-west-2" // specify your region you want to create 
  
}

resource "aws_instance" "Your_server" {
  ami           = "amia79a"
  instance_type = "t2.micro"

  tags = {
    Name = "Rahul_Example"
  }
}
