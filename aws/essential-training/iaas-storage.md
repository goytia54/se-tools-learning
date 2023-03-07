# Storage

## Elastic Block Storage
* Sits closer to hard ware, os and application code

## Elastic File System
* Like a NAS (network attached storage)
* Data things need to share
* Can mount to drive, and ec2 instance
* Need to give access from ec2 so you can mount

## S3 Simple Storage Service
* Like dropbox
* Slower then EFS and EBS
* Don't expose files you don't want. Keep public and private buckets to keep things seperate
* Don't put the key onto the server

## IAM Roles
* You can give a ec2 instance a role so it has acceess to the bucket

## S3 Glacier
* Only put data that infrequently used, wait sometime to access

## CloudFront
* Push contents to edge servers all over the world
* Content Delivery Network
