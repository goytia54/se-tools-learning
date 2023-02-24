# IaaS Compute

## Create EC2
* Search for EC2
* Launch instance, amazon machine images (AMI)
* You can select what hard ware you want
* Need to create a key pair to access the instance
* Can edit the name to have it custom
* Can connect to the running instance with instructions
* Difficult to get key back, put in a password manager

## EC2 Types
* Based on t shirt sizes
* Can have other type of instances such as GPUs

### Reserved Instance
* Pay up front for the next year
* Pay half up front for one year pay rest monthly
* Pay monthly for year

## Set up a web server
* Install apache

## Security Groups
* Act as simple firewalls
* Can expose only certain parts on a server
* red and black border, or red box around single EC2
* launch-wizard-# (automatically connected)

### In bound and out bound
* In bound is what can access
* Out bound is what the ec2 can access
* Can restrict both

## Autoscaling
* Key word is elastic, stretch and shrink

### Actions

#### Instance State
* Start, Stop, Reboot

#### Create the image
* Creates a snap shot and select a different availability zone to duplicate region
