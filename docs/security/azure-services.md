---
title: Azure services used (customer-friendly inventory)
---

This page provides a high-level inventory of Azure services commonly used by ProPM Agent when deployed as a Managed Application.

> Exact services may vary by configuration and region.

| Azure service | Purpose in ProPM Agent | Enterprise benefit | Security posture (high level) |
|---|---|---|---|
| Azure Marketplace Managed Application | Distribution and deployment | Consistent procurement and deployment | Deployed into customer tenant and subscription |
| Azure API Management | Single governed API entry point | Central policy and governance | Auth enforcement, controlled ingress |
| Azure Container Apps | Hosts application services | Elastic scale, managed operations | Internal services not publicly exposed |
| Azure Virtual Network | Network boundary | Isolation and control | Segmented subnets |
| Private Endpoints + Private DNS | Private access to PaaS services | Reduce exposure to public internet | Private connectivity |
| Azure Key Vault | Secret and key management | Central security control | Restricted access |
| Azure SQL Database | Relational project and identity metadata | Enterprise-grade relational store | Private connectivity |
| Azure Cosmos DB | Operational and audit/event data | Scale and flexible schema | Private connectivity |
| Azure Blob Storage | Document storage | Durable storage and lifecycle controls | No public blob access |
| Azure AI Search | Knowledge retrieval | Fast search with relevance | Private connectivity |
| Azure OpenAI | AI model inference | Enterprise AI capabilities | Private connectivity |
| Azure AI Document Intelligence | Document text extraction (when enabled) | Better document processing | Private connectivity |
| Azure Service Bus | Asynchronous processing | Reliability and decoupling | Private connectivity |
| Azure Event Grid | Event routing | Event-driven ingestion | Private connectivity |
| Azure Monitor + Log Analytics + Application Insights | Observability | Operational visibility | Controlled telemetry |

