# Deploy a high-availability web app using CloudFormation
In this project, I have deployed web servers for a highly available web app using CloudFormation. I have written the code that creates and deploys the infrastructure and application for a demo app from the ground up. I began with deploying the networking components, followed by servers, security roles and software. I have followed industry following best practices and have used scripting as much as possible.

<br>

### Features

`1.` Entire application can be taken down and brought back up using CloudFormation scripts in this repo.

`2.` Web servers are deployed in 2 different AZs inside a single region with auto-scaling capability.

`3.` EC2 instances are secured in a private subnet and only accepts traffic originating from a bastion host and load-balancer both within a public subnet.

`4.`  Load-balancer, bastion host, and web servers have security groups defined with only needed ports opened.

`5.`  Web servers have outbound internet access via NAT gateway for critical OS updates and patches.

`6.`  Sample application code is packaged and stored in an S3 bucket with IAM permissions.

`7.`  Web servers are configured with IAM instance profile to be able to access and download application code from AWS S3 bucket.

`8` Health checks and thresholds are defined to aid in system availability detection.

<br>

### Detailed Infrastructure Architecture

<p align="center">
    <img src="./HA-WebApp-Infrastructure.png" alt="arch diagram">
</p>

<br />

### Steps
`1.` Run ./create infra infra.yml infra.json

`2.` Run ./create servers servers.yml servers.json

`3.` Verify the application using DNS url

`4.` Run ./delete servers

`5.` Run ./delete infra