# {{ config.site_name }}

{{ config.site_description }}

## What is Cloud Computing?

On-demand delivery of compute, storage, applications and other IT resources.

### Problems with traditional IT approach

- Have to rent space in the data centre.
- Have to pay for power supply, cooling, maintenance.
- Time required to add/replace hardware.
- Limited scalability.
- Needs 24x7 team to monitor infrastructure.
- Have to manage DR events.

### Benefits of Cloud Computing

- Pay as you go pricing.
- Rapidly provision the right type & size of compute resources as required.
- Simple way to access servers, storage, databases and application services.
- Network connected hardware managed by AWS

### Deployment Models

#### Private Cloud

- Used by single organisation.
- Not exposed to the public.
- Provides security for sensitive applications.
- Meets specific business needs.

#### Public Cloud

- Resources owned/managed by third-party cloud service provider.

#### Hybrid Cloud

- Mix of private and public cloud.
- Control sensitive parts of your infrastructure, but leverage flexibility/cost effectiveness of public cloud.

### Characterics of Cloud Computing

| Characteristic                   | Description                                                                        |
|----------------------------------|------------------------------------------------------------------------------------|
| On-demand service                | Users provision/use resources without human interaction from the service provider. |
| Broad network access             | Resources available over the network, accessible from diverse client platforms.    |
| Multi-tenancy & resource pooling | Multiple customers share the same infra & applications (with security/privacy).    |
| Rapid elasticity and scalability | Automatically/quickly scale up & down as needed.                                   |
| Measured service                 | Usage is measured, only pay for what you use.                                      |

### Advantages of Cloud Computing

| Advantage              | Description                                                |
|------------------------|------------------------------------------------------------|
| Trade CAPEX for OPEX   | Pay as you go, reduces TCO and OPEX.                       |
| Economy  of scale      | Reduced prices due to large scale of AWS.                  |
| Stop guessing capacity | Scale based on measured usage.                             |
| Speed & agility        | Rapidly scale up/down, re-design infrastructure as needed. |
| Global reach           | Leverage AWS global infrastructure.                        |

### Problems solved by Cloud Computing

- **Flexibility** - Change resource types as they're needed.
- **Cost Effectiveness** - Pay as you go based on actual usage.
- **Scalability** - Easily scale horizontally or vertically.
- **Elasticity** - Rapidly scale up/down based on demand.
- **High availability/Fault tolerance** - Build cross multiple data centres.
- **Agility** - Rapidly develop, test and deploy applications.

### Types of Cloud Computing

| Type                               | Description                                                                                               |
|------------------------------------|-----------------------------------------------------------------------------------------------------------|
| Infrastructure as a Service (IaaS) | Networking, computers, storage. Highest level of flexibility and can run side-by-side with on-prem infra. |
| Platform as a Service (PaaS)       | Organisation doesn't have to manage the infrastructure. Focuses on deployment/management of applications. |
| Software as a Service (SaaS)       | Complete product managed by the service provider.                                                         |

## AWS Pricing Model

- Pay for compute.
- Pay for storage.
- Pay for data transfer out of the cloud (data transfer in is free).

## AWS Global Infrastructure

- **Region** - Cluster of data centres. Chose a region based on compliance requirements, proximity to customers, available services in that region, and pricing.
- **Availability Zone** - One or more data centres with their own power, networking etc. Each region as a minimum of 2, max of 6, typically there's 3.
- **Data Centre** - Self explanatory..
- **Edge Location/Point of Presence** - 205 edge locations, and 11 regional caches in 84 cities and 42 countries. Content delivered with lower latency.

## Shared Responsibility Model

### Customer

Customers are resposible for security in the cloud -

- Customer data.
- Platform.
- Applications.
- IDAM.
- Encryption.
- Network traffic security.

### AWS

Responsible for security of the cloud - 

- Infrastructure, hardware, software and internal security.
