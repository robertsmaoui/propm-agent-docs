---
title: Concepts
---

This page explains the core concepts used throughout ProPM Agent.

## Tenant

Your organization’s **tenant** is your Microsoft Entra ID directory. ProPM Agent uses Entra ID for sign-in.

## Project

A **project** is the main workspace boundary in ProPM Agent.

Most actions (Knowledge, Agents, PM Docs, AI Log) happen in the context of a selected project.

## Knowledge

**Knowledge** is your project’s document library:

- You can upload files into a project.
- Uploaded files become searchable.
- Search results include **sources** (citations) to support verification.

## Agents

An **agent** is a specialized assistant you can chat with in the context of a project.

Examples include a “Virtual Project Manager” and specialist roles (e.g., governance, risk, schedule).

## Runs

An agent interaction produces a **run** with a status (queued/running/completed/failed). Runs can be reviewed in the **AI Log**.

## PM Docs

**PM Docs** are project artefacts stored in the application. When available, you can:

- Open and edit content
- Mark a document as draft or final
- Download a DOCX export
- Optionally add an artefact into Knowledge

## Roles

ProPM Agent uses roles to apply the principle of least privilege.

At a minimum, you will see these roles in the product:

- **Project Owner** — full project control (members/roles, agent configuration, categories)
- **Project Manager** — runs agents and manages day-to-day project work
- **Contributor** — contributes content and runs agents
- **Viewer** — read-only access
- **Auditor** — read-only access with audit-focused visibility

Some admin pages also require a **Tenant Admin** role.

## Trace ID

Some screens display a **trace ID**. If you contact support, including the trace ID can help an administrator locate the relevant activity in operational logs.

