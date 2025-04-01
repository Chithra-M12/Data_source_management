backend.tf
terraform {
  backend "s3" {
    bucket = "state-management-backend-bucket"
    key    = "data_source.tfstate"
    region = "us-east-1"
  }
}

eip.tf
resource "aws_eip" "lb" {
  domain = "vpc"
}

output "eip_addr" {
  value = aws_eip.lb.public_ip
}
