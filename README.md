# Infrastructure Provisioning

A **_declarative infrastructure provisioning_** solution powered by **_Terraform_**, containerized with **_Docker_**. This setup automates **_edge networking_**, **_DNS management_**, and **_Cloudflare Zero Trust Access_** by leveraging **_Infrastructure as Code_** (**_IaC_**) principles across cloud endpoints and local services.

## Features

- **_Declarative infrastructure provisioning_** using **_Terraform_** for stateful Cloudflare resource management.
- **_Docker-based execution environment_** providing a consistent, isolated controller setup across platforms.
- **_Modular architecture_** leveraging structured **_HCL configurations_** for edge routing and access control.
- **_Centralized state synchronization_** powered by **_Terraform Cloud_** to maintain consistent execution state between local environments and CI/CD pipelines.

## Configuration Files

|                                   File                                   | Description                                                                                                                                   |
| :----------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------- |
|        [`cloudflare_access.tf`](./terraform/cloudflare_access.tf)        | Configures **_Cloudflare Zero Trust Access policies_**, **_application rules_**, and **_authentication requirements_** for secure edge access |
|           [`cloudflare_dns.tf`](./terraform/cloudflare_dns.tf)           | Provisions **_DNS CNAME_** and **_A records_** to route traffic across homelab services and external endpoints                                |
| [`cloudflare_email_routing.tf`](./terraform/cloudflare_email_routing.tf) | Configures **_Cloudflare Email Routing_** rules and custom address forwarding for the root domain                                             |
|        [`cloudflare_tunnel.tf`](./terraform/cloudflare_tunnel.tf)        | Creates and manages **_Cloudflared tunnels_** and **_ingress rules_** for secure, outbound-only network exposure                              |
|                [`providers.tf`](./terraform/providers.tf)                | Defines required **_Terraform providers_**, version locks, and remote **_backend state_** configurations                                      |

## Configuration Setup

1.  **Initialize Working Directory:**

    ```bash
    terraform init
    ```

2.  **Validate Plan:**

    ```bash
    terraform plan
    ```

3.  **Apply Changes:**

    ```bash
    terraform apply
    ```
