# Python Environment Project
## Timings
2 Days

## Summary


We have a created a console JSON application that can gather data from IT Jobs Watch.


Your job is to create working development, testing and production environment and to build a pipeline to move the code through them using Jenkins. This will include your application and configuration code.



Note: We will need to add the group to Repo on GitHub before it is accessible.



You can clone the code for the application from the following repo:

```
https://github.com/spartaglobal/It_Jobs_Watch_Data_Package
```

You should fork this repo to one of your own and then clone between the group.


## Tasks


## Python App Pipeline

- Create a development environment using Vagrant and provision it with Bash such that it can run the application successfully.
	Your development environment needs testing too.
- Create a Jenkins job that listens for Webhooks from your forked repo and starts a testing job on the Python Slave node.
- Create a Python slave node on the Jenkins instance. For this you will need to create an AMI through AWS, this is an Amazon Machine Image that is provisioned via your Bash script. Check you can run the App before you creating the AMI. (You have not done this yet - Research will be needed on creating an AMI from an EC2 instance and then creating a Python Slave Node via the EC2 plugin on Jenkins).
	Run the tests in the application on the slave node, this should show a successful build when the tests pass.



## Deliverables



1. Forked ItJobsWatch application repo with Vagrantfile ability to simply Vagrant up and run in development
2. Jenkins Job that runs test suite on pushes to master branch of forked application repo.
3. Python Slave node created via AMI
