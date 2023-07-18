# IAM Roles for a startup

## Goal

To provide the initial hand holding for the business owner with setting up IAM Roles with basic templates to expedite the process of moving you to AWS. After all, security is of utmost importance, especially starting out. Not starting with the right structure is going to cause accumulation of technical debt.

This project focuses on creating a skeleton of IAM roles for startups moving to AWS. This provides the company with the ability to get started with little or no modifications. For new companies (and even old companies), time is money. The less time you need to spend setting up permissions structures in AWS, the more money you have to build your company in other ways.


## Role of Security


In this project, we try to place security above everything. We are trying to avoid accidental deletions. We are assuming that every team member will log in from known IPs. As an added layer of security, we are making MFA mandatory for every user that logs in, even admins. To add the mandatory MFA, there is a policy called ```force_mfa.json``` that will need to be created and added to a group called ```FORCE_MFA```. Each IAM user to be created, will need to be a part of the ```FORCE_MFA``` group. This policy will deny IAM user's access to AWS resources until they add their MFA and use it to authenticate.


## Assumptions

Based on best practices in AWS, we are working with the following assumptions:

- Presence of generic job roles.
- Every user will log in from the companies external IP
- Use of blacklist instead of whitelist to keep the roles tidy.


## Job Profiles

Job profiles across different verticals, i.e: business, finance, tech and ops.


## Setting Up Roles

For reach role that you are going to use, follow these steps:

- Open the IAM Console in your AWS Account.
- Click Policies and then Create Policy.
- Click Groups and Create Groups. For the attached policy, choose the policy created above.
- Click on the group you just made, and hit Add Users To Group. Add all users that fit this group.
- ALL users need to be added to the FORCE_MFA group which has the FORCE_MFA policy attached.
