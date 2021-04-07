# EC2

## Overview

- Need to activate IAM access to allow IAM users/federated users to access billing information.
- EC2 covers virtual machines, data storage on virtual drives (EBS), load balancing (ELB) and auto-scaling (ASG).
- Use an EC2 instance role to give an instance permissions to interact with other AWS services. Don't run ```aws configure``` on the instance because it might be shared with other users.

##  Budgets

- Can create a budget under Cost Management.
- Can be a reoccuring, or expiring budget.
- Budget amount can be fixed (same limit each month), or based on a monthly budgeted amount (varying limits based on the monnth).
- Can aggregate costs by pre-defined categories, and include related costs such as tax, support charges etc.
- Alerts can be based on a percentage of actual, or forecasted costs.
- Budget can have multiple alerts.
- Alerts go to an e-mail address, or Slack/Chime via the AWS Chat bot.

## Sizing & Configuration Options

Sizing/configuration can be based on -

- **OS** - Windows or Linux.
- **CPU** - Computer power, and number of cores.
- **Memory** - How much RAM is required.
- **Storage** - Network attached (EBS and EFS), or hardware (EC2 instance store).
- **Network** - Speed, public IP address.
- **Firewall  rules** - Defined using security groups.
- **Bootstrap script** - EC2 user data that's executed at first launch of the EC2 instance.

## Instance Types

| Type                           | Good For                                                                                                                                                                                                 |
|--------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| General Purpose                | Web servers, code  repositories. Balance between compute, memory, networking.                                                                                                                            |
| Compute Optimized              | Batch processing, media transcoding, high performance web server/computing, Scientific modelling & machine learning, gaming servers.                                                                     |
| Memory Optimized               | Processing large in-memory data sets. Floating point number calculations, Graphic processing, Data pattern matching.                                                                                     |
| Storage Optimized              | Storage intensive tasks that need high UI. High frequency online transaction processing, relational/NoSQL databases, cache for in-memory databases (Redis),  Data warehousing, Distributed file systems. |

## Security Groups

- Firewall rules that can control traffic in/out of EC2 (IPv4 or IPv6).
- Only contain **allow** rules.
- Can reference by IP, or security group.
- Defines type (HTTP, SSH, custom), protocol (TCP, UDP), port range, source (anywhere, single IP, or CIDR) and rule description.
- A connect timeout on EC2 probably means a problem with the security group rules.

## SSH

- Make sure private key permissions are 0600 (or make yourself owner of the private key on Windows 10, and remove any other groups/users).

### EC2 Instance Connect

- Web based SSH terminal accessible through the management console.

### SSH Troubleshooting

- Connection timeout likely means an issue with the security groups, or corporate firewall/proxy.
- Connection refused means SSH isn't running on the instance. Throw it away and provision a new one.
- Permission denied means the ssh key permissions are wrong, the key is wrong, or you're using the wrong user.
- Use EC2 instance connect as a last resort if needed.

## EC2 Instance Purchasing Options

### EC2 On Demand

- Pay for what you use (per second for linux, per hour for windows).
- Suitable for short-term, uninterupted workloads, predictable pricing.
- Highest cost.
- No upfront payment.
- No long term committment.

### Reserved

- Slightly cheaper than On Demand.
- Suitable for steady state, long running workloads (databases etc).
- Reservation period of 1 or 3 years (must be one or the other. Can't be 2 years).
- Can pay upfront, partially upfront, or no upfront payment. The more you pay in advance, the more you save.
- Reserve a specific instance type (t2.micro etc).
- Convertible reserved instance is  good for long workloads with flexible instances (can change the type).
- Scheduled reserved instances are good for specific time windows over 1-3 years (eg: Thursdays from 3pm - 6pm).

### Spot

- Highest discount.
- Suitable for workloads that are resilient to failure (batch jobs, image processing, distributed workloads etc)..
- Can be lost at any time, if the max price you're willing to pay is less than the spot price.

### Dedicated Hosts

- Book an entire physical server, control instance placement.
- Suitable where there's special compliance requirements, or where you need to use existing server-bound software licenses.
- More access to the underlying hardware (sockets, cores, host id).
- Allocated for 3 years.
- Expensive.

### Dedicated Instances

- Instance running on hardwre dedicated to you.
- May share hardware with other instances in the same account.
- No control over instance placement, but you can move hardware after a Stop/Start).
- Per instance billing.

## Shared Responsibility Model

**AWS** are responsible for -

- Infrastructure (global network security).
- Isolation on physical hosts.
- Replacing faulty hardware.
- Compliance validation.

**Customers** are responsible for -

- Security Group rules.
- OS patches and updates.
- Above base software/utilities installed on the instance.
- IAM roles assigned to the instance.
- IAM user access management.
- Data security on the instance.
