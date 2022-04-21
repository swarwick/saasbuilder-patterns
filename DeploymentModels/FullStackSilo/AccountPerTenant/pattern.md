## Accounts Per Tenant

### Core Concept
* There are many ways to deploy a SaaS solution. Compliance, isolation, noisy neighbor, tiering and other considerations can have lead you to deploy your SaaS offering in any number of different deployment patterns that best align with the business and operational goals of your SaaS environment. These deployment models are not mutually exclusive. Some SaaS businesses may opt to support multiple deployment models to address the specific and personas of their customer base.

### Key Considerations
* While you can automate aspects of each tenant accounts, there are some aspects of account configuration that cannot be achieved through automation. Account limits are amongst this list and represent a key area you’ll want to consider as you look at what limits will need to be adjusted for each new tenant account.
* AWS Control Tower provides tools for orchestrating the provisioning and configuration of accounts. It provides mechanisms that can simplify this deployment and introduce guard that may enhance the overall security and isolation footprint of your SaaS offering.
* While we’re siloing resources, we are not allows tenants to run separate versions of the product. The operational experience here inherits the job of providing a single pane of glass that can provides an aggregated view of all the tenant environments. Application deployments will send all data to all tenants.
* The control plane of your SaaS environment will need access to all tenant accounts. This means you’ll need to configure and enable cross-account access, opening up paths for your control plane to deploy, operate, and manage tenant environments.
* Any account-per-tenant model needs to consider the overall scaling profile of your SaaS environment. Your number of tenants may exceed account limits, for example. Also, managing and operating large numbers of tenants in an account-per-tenant model can be challenging. Aggregation of operational data, deployments, and a host of other areas get more complex in environments with a large number of tenant accounts.



