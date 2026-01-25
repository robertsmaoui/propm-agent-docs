---
title: Create an installation (step-by-step)
---

This page walks a tenant admin through deploying ProPM Agent from Azure Marketplace.

## Who can do this

- **Tenant Admin / Installer**

## Before you begin

Complete the checklist in **Install via Azure Marketplace → Prerequisites**.

## Steps

1. In Azure Portal, open the **ProPM Agent** offer in **Azure Marketplace**.
2. Select **Create**.
3. In the Basics step, choose:
   - **Subscription**
   - **Resource group**
   - **Region**
4. In **Application Settings**, fill in the following fields:

   ### **Environment Name**
   A short label to distinguish environments (for example, `dev` or `prod`).

   ### **Application (Entra) Client ID**
   The **Application (client) ID** of your Entra app registration.

   ### **Authority (Entra ID)**
   The Entra authority used for sign-in.

   - For single-tenant deployments, use your tenant-specific authority.
   - For multi-tenant testing, you can use the `common` authority.

   ### **Scopes (comma-separated)**
   Scopes used during sign-in.

   Your identity team may provide the exact value. A typical pattern is:

   - `openid,profile,api://<your-client-id>/.default`

   ### **CORS Allowed Origins** (optional)
   Usually leave this empty. Provide a value only if you need to allow additional web origins.

   ### **Azure SQL Admin Password**
   A strong password used for initial database provisioning.

   ### **VNet CIDR**
   A private network range (CIDR) available for the deployment.

5. Select **Review + create**.
6. When validation completes, select **Create**.
7. Wait for deployment to complete.

## Expected results

After deployment completes, you can open the Managed Application resource and find the web application URL.

## Common issues

- **Validation fails for the Client ID**: confirm you pasted the **Application (client) ID** (a GUID), not another identifier.
- **Authority format is rejected**: enter a valid HTTPS authority URL.
- **Deployment fails due to networking**: confirm the **VNet CIDR** does not overlap with existing address ranges.

