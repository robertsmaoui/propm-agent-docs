---
title: Sign-in issues
---

## Symptoms

- You cannot sign in.
- Sign-in works, but you see an error page.

## What to check

1. Confirm you are using the correct ProPM Agent URL.
2. Confirm your account is allowed to sign in (your organization controls this in Entra ID).
3. If you see a redirect error, ask your tenant admin to confirm the application registration has the correct redirect URI.
4. Ensure the deployment uses your **tenant ID** (single-tenant per customer).

## If the issue persists

- Capture any displayed **trace ID**.
- Contact your tenant administrator.

## Unauthorized client / AADSTS700016

If you see:

> `AADSTS700016: Application with identifier '<client-id>' was not found in the directory ...`

This means the client ID is not in the tenant used for sign‑in. Fix by confirming the tenant and app registration.


### AZ CLI checks

```bash
# Login to the tenant used during deployment
az login --tenant <TENANT_ID>

# Verify the application exists
az ad app show --id <CLIENT_ID>

# Verify the service principal exists (enterprise app)
az ad sp show --id <CLIENT_ID>
```

If `az ad app show` fails, the client ID is from another tenant. Create a new app registration in the correct tenant and update the Marketplace parameters.

