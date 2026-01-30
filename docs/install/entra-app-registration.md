---
title: Identity prerequisite — customer-owned Entra app registration
---

ProPM Agent uses **Microsoft Entra ID** for user sign-in.

This means your organization must provide (and manage) an **Entra app registration**.

## Why this matters

- Your tenant controls who can sign in.
- Your security team can review and manage the identity configuration.
- Roles and access can be managed through Entra users and groups.

## High-level steps (admin)

1. Create an **App registration** in Microsoft Entra ID.
2. Record the **Application (client) ID**.
3. Configure the app registration for web sign-in:
   - Add the deployed ProPM Agent web URL as a **redirect URI**.
4. Define and assign application roles (recommended):
   - Tenant Admin
   - Project Owner
   - Project Manager
   - Contributor
   - Viewer
   - Auditor

## Notes on timing

The web application URL is generated during deployment. In many organizations:

1. You create the app registration first (to get the **client ID** required by the Marketplace wizard).
2. After deployment, you update the app registration to include the deployed web URL as a redirect URI.

## AZ CLI (single-tenant) quick start

Use these commands **in the customer tenant**.

> Replace placeholders: `<APP_NAME>`, `<WEB_URL>` (the deployed web URL), `<TENANT_ID>`.

```bash
# Login to the customer tenant
az login --tenant <TENANT_ID>

# Create the app registration (single-tenant)
APP_ID=$(az ad app create \
  --display-name "<APP_NAME>" \
  --sign-in-audience AzureADMyOrg \
  --web-redirect-uris "<WEB_URL>" \
  --query appId -o tsv)

echo "Client ID: $APP_ID"

# (Optional) Expose an API scope so you can use api://<clientId>/.default
az ad app update --id $APP_ID --set api.requestedAccessTokenVersion=2

# Create a service principal (enterprise app) for assignments
az ad sp create --id $APP_ID
```

### Suggested scopes for Marketplace parameters

- `authClientId` = `APP_ID`
- `authAuthority` = `https://login.microsoftonline.com/<TENANT_ID>`
- `openidConfigUrl` = `https://login.microsoftonline.com/<TENANT_ID>/v2.0/.well-known/openid-configuration`
- `authScopes` = `openid,profile,api://<clientId>/.default`

## Common issues

- **Sign-in succeeds but you see “Access denied”**: your user is authenticated, but you are missing required application role assignments.
- **Sign-in fails with a redirect error**: the redirect URI configured in Entra does not match the actual deployed web URL.

