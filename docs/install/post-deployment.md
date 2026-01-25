---
title: Post-deployment — find the app URL and sign in
---

Once the Marketplace deployment finishes, you can access ProPM Agent.

## Who can do this

- **Tenant Admin / Installer**
- **Project Owner / Project Manager / Contributor / Viewer / Auditor** (sign-in)

## Steps

1. In Azure Portal, open the **Managed Application** resource created by the deployment.
2. Locate the **outputs** or **deployment outputs** section.
3. Copy the **web application hostname / URL**.
4. Open the URL in a browser.
5. Select **Sign In with Microsoft**.

## Expected results

- You can sign in successfully.
- You land on the **Dashboard**.

## Verify access quickly

After sign-in, try one simple action:

1. Open **Projects**.
2. Confirm you can see at least one project or (if you are a Project Owner) that you can create one.

## Common issues

- **You can’t sign in**: confirm the Entra app registration has the correct redirect URI (see the Entra prerequisite page).
- **Access denied after sign-in**: confirm your account has been assigned the appropriate ProPM Agent role in Entra ID.

