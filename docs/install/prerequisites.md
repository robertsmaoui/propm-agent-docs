---
title: Prerequisites checklist
---

Before you deploy ProPM Agent from Azure Marketplace, confirm you have the following.

## Azure subscription and permissions

- An Azure subscription where you are allowed to deploy **Managed Applications**.
- Permission to select or create a **resource group**.
- Permission to deploy into a supported **region**.

## Identity (Microsoft Entra ID)

- A **customer-owned Microsoft Entra application registration** prepared for ProPM Agent sign-in.
- The **Application (client) ID** for that registration.
- The **Tenant ID** of the customer directory (GUID).

> Each customer uses their own **single-tenant** Entra app registration and tenant ID.

## Network plan

- A **virtual network CIDR range** available for the deployment.
  - Use a non-overlapping private CIDR range.
  - If you are unsure, coordinate with your network team.

## Database provisioning input

- A strong **Azure SQL admin password** (minimum 12 characters).

## Optional: CORS origins (only if needed)

- If you plan to access the API from additional web origins (for example, custom domains), prepare the list of allowed origins.

## What you will provide during deployment

You will be asked for these values in the Marketplace deployment wizard:

- **Environment Name**
- **Application (Entra) Client ID**
- **Tenant ID (Entra ID)**
- **Scopes**
- **CORS Allowed Origins** (optional)
- **Azure SQL Admin Password**
- **VNet CIDR**

