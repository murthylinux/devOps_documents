#  Terraform scripts: 

```
# simple script:
provider "aws" {
    region = "ap-south-1"
}

resouce "ec2_instance" "devopsec2" {
    ami = ""
    instance_type + "t2.micro"


    tags = {
        Name = "devopsec2"
    }
}
```
```
# incremental script:
resource "aws_instance" "example" {
  count = 10
  ami           = "ami-0c94855ba95c71c99"
  instance_type = "t2.micro"

  tags = {
    Name = "Instance-$(count.index)"
  }
}
```








```
