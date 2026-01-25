---
title: Network posture (private-by-default)
---

ProPM Agent is deployed to Azure with an enterprise network posture.

## High-level posture

- End users access the application through the **web UI**.
- The web UI communicates through a **single API entry point**.
- Internal services and data services are not intended to be directly exposed to the public internet.

## Why this matters

Reducing exposed surfaces helps align with common enterprise security review expectations.

