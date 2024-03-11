<img width="100%" valign="bottom" src="https://github.com/AhmedAboulnaga/test/blob/main/assets/banner.png"/>

## Introduction

This repository includes all source code to automatically deploy an Azure-based data infrastructure that supports capabilities to query and analyze data. The focus of the solution was to create an idempotent cloud data infrastructure that can be repeatedly deployed automatically for multiple environments using cloud-native frameworks.
<details open>
<summary>
 Features
</summary> <br />
For this exercise, Team REI utilized the following features and capabilities.<br/><br/>
  
<p align="center">
    <img width="49%" src="https://github.com/AhmedAboulnaga/test/blob/main/assets/feature1.png"/>
&nbsp;
    <img width="49%" src="https://github.com/AhmedAboulnaga/test/blob/main/assets/feature2.png"/>
</p>

<p align="center">
    <img width="49%" src="https://github.com/AhmedAboulnaga/test/blob/main/assets/feature3.png"/>
&nbsp;
    <img width="49%" src="https://github.com/AhmedAboulnaga/test/blob/main/assets/feature4.png"/>
</p> 

<p align="center">
    <img width="49%" src="https://github.com/AhmedAboulnaga/test/blob/main/assets/feature5.png"/>
&nbsp;
    <img width="49%" src="https://github.com/AhmedAboulnaga/test/blob/main/assets/feature6.png"/>
</p> 

<p align="center">
    <img width="49%" src="https://github.com/AhmedAboulnaga/test/blob/main/assets/feature7.png"/>
&nbsp;
    <img width="49%" src="https://github.com/AhmedAboulnaga/test/blob/main/assets/feature8.png"/>
</p> 

<p align="center">
    <img width="49%" src="https://github.com/AhmedAboulnaga/test/blob/main/assets/feature9.png"/>
</p> 

</details>

## Architecture

The following diagram illustrates the cloud services and components that comprise our final architecture.

<p align="center">
<img width="100%" src="https://github.com/AhmedAboulnaga/test/blob/main/assets/architecture.png"/>
</p>

### Video Walkthrough

This recording is an actual end-to-end recording of the provisioning process of the production environment through GitLab Runner, taking a total of 12 minutes and 44 seconds.

<p align="center">
<img width="100%" src="https://raw.githubusercontent.com/Skydio/revup/main/docs/images/tutorial_1.gif"/>
</p>

## Assumptions

Based on the scenario, the team has put forth a few assumptions in regards to the overall solution.
- The Azure Account, Subscription and Enterprise Application Service Principal will already be in place before the automated deployment of IaC. 
- The end-to-end solution is built to meet the full requirements of the scenario. 
- The evaluation team will have the necessary permissions (i.e. elevated privilege accounts) to deploy Infrastructure within the FEMA Enterprise Cloud (similar to the FEC team) as services need to be deployed outside of the FEMADex Development team responsibilities.
- The team has replicated least-privileged Role-Based Access Controls to the data infrastructure through local group policies that simulates Azure Active Directory access controls within the automated deployment. User Personas, roles and responsibilities are documented in this repository: https://

## Prerequisites

To deploy the infrastructure, the SecDevOps Engineer will need to have access to the following services (locally or a jump box/bastion host) that can communicate with Azure services.
- Terraform
- Software to run Git commands (i.e. Git Bash)
- Azure CLI

## Deployment Instructions

Instructions to deploy the infrastructure are broken down into 5 steps and available in the repository: https://gitlab.com/femadextech/iacmain/-/blob/develop/prep/setup-instructions.txt

1. Prepare Azure Subcription and Entra ID/AAD Service Principal.
2. Configure prepartion shell script (prep.sh) with variable declarations within the section marked 'change'.
3. Configure Gitlab CI/CD variables within the repository.
4. Executing the Gitlab pipelines will deploy the multiple environments (for this exercise - Dev, Test, Prod).
5. Drift Detection can be scheduled via Runner Pipeline.

## Test and Deploy

As a part of the package, there is a Drift Test Pipeline (described in step 5 of deployment instructions). This test is performed against the current environment deployed against the ideal Terraform state and identifies any differences in the infrastructure. https://gitlab.com/femadextech/iacmain/-/pipeline_schedules

<br/>
<hr/>
<br/>

## Support

For any questions, comments or concerns, please reach out to brian.robertson@reisystems.com.

## Roadmap

The supporting artifacts located in this repository contains a backlog and schedule of milestones. This is located: https://

