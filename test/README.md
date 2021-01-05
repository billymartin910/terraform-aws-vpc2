### Module will create VPC with 3 public & 3 private subnets 

```
module "VPC" {
  source              = "billymartin910/vpc2/aws"
  region              = "us-east-1"
  cidr_block          = "10.0.0.0/16"
  private_cidr_block1 = "10.0.1.0/24"
  private_cidr_block2 = "10.0.2.0/24"
  private_cidr_block3 = "10.0.3.0/24"
  public_cidr_block1  = "10.0.101.0/24"
  public_cidr_block2  = "10.0.102.0/24"
  public_cidr_block3  = "10.0.103.0/24"

  tags = {
    Name        = "VPC_Project"
    Environment = "Dev"
    Team        = "DevOps"
    Department  = "Operations"
    Bill        = "CFO"
    Quarter     = "1"
  }
}
```

### Output Information

```

output "vpc_id" {
  value = "${aws_vpc.main.id}"
}

output "private_subnet1" {
  value = "${aws_subnet.subnet1.id}"
}

output "private_subnet2" {
  value = "${aws_subnet.subnet2.id}"
}

output "private_subnet3" {
  value = "${aws_subnet.subnet3.id}"
}

output "public_subnet1" {
  value = "${aws_subnet.subnet101.id}"
}

output "public_subnet2" {
  value = "${aws_subnet.subnet102.id}"
}

output "public_subnet3" {
  value = "${aws_subnet.subnet103.id}"
}

output "tags" {
  value = "${var.tags}"
}

```