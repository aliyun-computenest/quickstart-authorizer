# Authorizer Community Edition Quick Deployment

> **Disclaimer:** This service is provided by a third party. We strive to ensure its safety, accuracy, and reliability, but cannot guarantee it is entirely free of faults, interruptions, errors, or attacks. Therefore, our company hereby states that we make no representations, warranties, or commitments regarding the content, accuracy, completeness, reliability, applicability, or timeliness of this service, and shall not be liable for any direct or indirect loss or damage arising from your use of this service; regarding third-party websites, applications, products, and services accessed through this service, we are not responsible for their content, accuracy, completeness, reliability, applicability, or timeliness, and you should bear the risks and responsibilities resulting from the use; we will not be liable for any losses or damages arising from your use of this service, including but not limited to direct losses, indirect losses, loss of profits, loss of goodwill, loss of data, or other economic losses, even if the company was previously notified of the possibility of such losses or damages; we reserve the right to modify this disclaimer from time to time, so please check this disclaimer regularly before using this service. If you have any questions or concerns about this disclaimer or this service, please contact us.

## Overview
**Authorizer** is an open-source authentication and authorization solution for your applications. Bring your database and have complete control over the user information. You can self-host authorizer instances and connect to any database (Currently supports 11+ databases including [Postgres](https://www.postgresql.org/), [MySQL](https://www.mysql.com/), [SQLite](https://www.sqlite.org/index.html), [SQLServer](https://www.microsoft.com/en-us/sql-server/), [YugaByte](https://www.yugabyte.com/),  [MariaDB](https://mariadb.org/), [PlanetScale](https://planetscale.com/), [CassandraDB](https://cassandra.apache.org/_/index.html), [ScyllaDB](https://www.scylladb.com/), [MongoDB](https://mongodb.com/), [ArangoDB](https://www.arangodb.com/)).

Authorizer offer the following functionality

- ✅ Sign-in / Sign-up with email ID and password
- ✅ Secure session management
- ✅ Email verification
- ✅ OAuth2 and OpenID compatible APIs
- ✅ APIs to update profile securely
- ✅ Forgot password flow using email
- ✅ Social logins (Google, Github, Facebook, LinkedIn, Apple more coming soon)
- ✅ Role-based access management
- ✅ Password-less login with magic link login
- ✅ Multi factor authentication
- ✅ Email templating
- ✅ Webhooks

## Prerequisites

Deploying the Maybe community edition service instance requires access to and the creation of certain Alibaba Cloud resources. Therefore, your account needs to contain permissions for the following resources.  
**Note:** This permission is only required when your account is a RAM account.

| Permission Policy Name                        | Remarks                                              |
|-----------------------------------------------|-----------------------------------------------------|
| AliyunECSFullAccess                           | Permission to manage cloud server services (ECS)   |
| AliyunVPCFullAccess                           | Permission to manage Virtual Private Cloud (VPC)   |
| AliyunROSFullAccess                           | Permission to manage Resource Orchestration Service (ROS) |
| AliyunComputeNestUserFullAccess               | Permission to manage the user side of ComputeNest   |

## Billing Instructions

The costs associated with deploying the community edition in ComputeNest mainly involve:
+ The selected vCPU and memory specifications
+ The type and capacity of the system disk
+ Public network bandwidth

## Deployment Architecture

![](./img-en/deploy.png)

## Parameter Description

| Parameter Group                               | Parameter Item                                     | Description                                          |
|-----------------------------------------------|---------------------------------------------------|-----------------------------------------------------|
| Service Instance                              | Service Instance Name                             | Length not exceeding 64 characters, must start with a letter, can contain numbers, letters, hyphens (-), and underscores (_) |
|                                               | Region                                            | The region in which the service instance is deployed |
|                                               | Payment Type                                      | The billing type of the resource: pay-as-you-go or subscription   |
| ECS Instance Configuration                    | Instance Type                                     | Instance specifications available in the availability zone |
|                                               | Instance Password                                  | Length 8-30, must include three items (uppercase letters, lowercase letters, numbers, or special symbols from the set ()`~!@#$%^&*-+=|{}[]:;'<>,.?/)    |
| Network Configuration                         | Availability Zone                                 | The availability zone where the ECS instance is located |
|                                               | VPC ID                                           | The VPC where the resource is located               |
|                                               | Switch ID                                        | The switch where the resource is located            |

## Deployment Process

1. Visit the Compute Nest [deployment link](https://computenest.console.aliyun.com/service/instance/create/default?type=user&ServiceName=Authorizer%E7%A4%BE%E5%8C%BA%E7%89%88) and fill in the deployment parameters as prompted.
2. Fill in the instance parameters: ![](./img/param1.png)
3. Choose to create a new dedicated network or use an existing VPC as needed. Fill in the availability zone and network parameters: ![](./img/param2.png)
4. Click "Create Now" and wait for the service instance deployment to complete: ![](./img/param4.png)
5. Once the service instance is deployed, click on the instance ID to enter the detail page: ![](./img/serviceInstance2.png)
6. Access the URL for using the service instance: ![](./img/serviceInstance3.png)
7. The application provides a port that can be used directly by clicking.
8. Let's navigate to the login page and register an admin account. The username is fixed as "admin", and you can enter the password: ![](./img/app1.png)
9. After logging in, you can see the overall dashboard as shown: ![](./img/app2.png)
10. Various OAuth login methods are supported, such as Google, GitHub, etc.

