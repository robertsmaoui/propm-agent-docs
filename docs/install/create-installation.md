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

   ### **Entra Tenant ID**
   The tenant ID (GUID) of your organization’s Entra directory.
   This deployment uses **single-tenant** per customer.

   ### **Scopes (comma-separated)**
   Scopes used during sign-in.

   Your identity team may provide the exact value. A typical pattern is:

   - `openid,profile,api://<your-client-id>/.default`

   ### **AZ CLI helper (optional)**
   If you don’t already have an app registration, you can create one quickly:

   ```bash
   az login --tenant <TENANT_ID>

   APP_ID=$(az ad app create \
     --display-name "ProPM Agent" \
     --sign-in-audience AzureADMyOrg \
     --web-redirect-uris "<WEB_URL>" \
     --query appId -o tsv)

   az ad sp create --id $APP_ID
   echo "Client ID: $APP_ID"
   ```

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
- **Tenant ID format is rejected**: ensure you entered the **tenant GUID** (not a domain name).
- **Deployment fails due to networking**: confirm the **VNet CIDR** does not overlap with existing address ranges.

