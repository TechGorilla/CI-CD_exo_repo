# Situation
As DevOps Engineer you are part of a team building an application which consists of a Java backend and a React frontend. As the expert of the team in cloud and automation, you are supposed to lead	the	way	orchestrating and deploying the application to the cloud.
For	the	purpose	of	this assignment, we	have provided you with an attachment that contains a simple application	with the mentioned components plus an in-memory	database (it can remain	in	
memory for the purpose of the assignment).

# Indications

The	team together with the product owner and the scrum master, has defined the following user stories:

## Story 1

>As a DevOps engineer, I want to have a CI/CD pipeline for my application:\
>       - The pipeline must build and test the application code base.\
>       - The pipeline must build and push a Docker container ready to use.\
>       - The pipeline must deploy the application across different environments on the target infrastructure.
    
_Bonus point: Separate the backend and the frontend in different pipelines and containers._

## Story 2

> As a DevOps engineer, I want to have a pipeline to deploy the required infrastructure for my 
> application. The infrastructure must be created on the cloud, for the purpose of the assignment any public cloud can be used.\
>       - The deployment pipeline must use infrastructure as code (Cloud Formation, Cloud Deployment Manager, Azure Resource Manager or Terraform).\
>       - The delivered infrastructure must be monitored and audited.\
>       - The delivered infrastructure must allow multiple personal accounts.\
> For the purpose of the assignment, you will define the cloud architecture that you see fit, document it and explain the resources created and choices made.

_Bonus point: The delivered infrastructure must be able to scale automatically._ \
_Bonus point: Modify the application to make use of real database running on the cloud,	instead	of the in-memory database._

__TIP__: We'd highly appreciate if you provide cleanup/destroy functionality as part of the pipeline.

# Expected deliverables :
What do	we expect as a deliverable?\
    * Source code of the pipeline(s) and the IaC source code of the solution implemented.\
    * Instructions on how to fork, configure and deploy the solution on our own cloud environment.\
    * High-level documentation explaining the overall architecture of the solution implemented.
	

# Resolution

Create a new directory "CI-CD_EXO_REPO/" as main git repository.\
The solution to the assignment will be documented in the appropriate directory by Story.


