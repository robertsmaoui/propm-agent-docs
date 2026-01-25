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

## Common issues

- **Sign-in succeeds but you see “Access denied”**: your user is authenticated, but you are missing required application role assignments.
- **Sign-in fails with a redirect error**: the redirect URI configured in Entra does not match the actual deployed web URL.

