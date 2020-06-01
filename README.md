# kubernetes-cluster
```
kops create cluster \
# this is the name of our cluster \
--name=kops.example.com \
# this is S3 bucket on AWS (object storage) \
--state=s3://kops.example.com \
# Role base Authorization \
-- authorization RBAC \
# Availibility zone in US virginia \
--zones=us-east-1a \
# How many nodes \
--node-count=2 \
# how powerfull EC2 instance we want \
--node-size=t2.micro \
--master-size=t2.micro \
# How many masters in k8s cluster we want \
--master-count=1 \
# Hosted Zone - we need to create it in advance in AWS Route 53 \
# you can define your own name \
# make sure that you have your own domain name \
--dns-zone=kops.example.com \
# this is the name of output folder where \
# kops will generate => terraform code \
--out=example_terraform \
# target is "terraform" code \
--target=terraform