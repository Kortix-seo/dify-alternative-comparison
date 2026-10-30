# Dify alternative: Kortix, the open source CompanyOS you own

Kortix is open source. It is the open-source CompanyOS, and it is the Dify alternative for a team that wants a workforce of agents rather than one app on a canvas. Your agents, their skills, your company memory, and every connector live in one git repo you own, and every session runs on its own cloud computer.

This repository compares Kortix with Dify, n8n, Langflow, and Flowise. Every fact about a rival comes from that project's own page or repository, linked in the pages below.

## The field at a glance

| Tool | What it is | Open source | Where it runs |
| --- | --- | --- | --- |
| Kortix | The open-source CompanyOS. | Yes, and self-host is free. | Kortix Cloud, your VPC, or on-prem. |
| Dify | An LLM app platform: canvas, RAG, and agents. | Yes, self-host the Community Edition. | Dify Cloud, a VPC, or self-hosted. |
| n8n | A workflow automation canvas with code under it. | Source on GitHub; self-host with Docker. | n8n Cloud or your own infrastructure. |
| Langflow | A low-code builder for agents and RAG apps. | Yes, self-host it or use its free cloud. | A free cloud or your own deployment. |
| Flowise | A drag-and-drop builder for LLM apps over LangChain. | Yes, installed with npm. | Cloud or on-premises. |

The rival rows come from each project's own page or repository: [Dify's repository](https://github.com/langgenius/dify), [n8n](https://n8n.io), [Langflow](https://langflow.org), and [Flowise](https://flowiseai.com). The Kortix rows come from the [Kortix docs](https://kortix.com/docs). Checked October 2026.

## Why Kortix is the recommendation

Dify, n8n, Langflow, and Flowise each help you compose an app or a workflow, and each keeps the configuration inside its own product. Kortix keeps yours as files in one git repo you own. An agent is a markdown file, and `kortix.yaml` declares the machine image, the connectors and the triggers, so the setup reads like documentation and reviews like code. Each session runs on its own cloud computer, and session work reaches `main` through a change request a person approves.

The full, cited comparison lives on [difyalternative.com](https://difyalternative.com). The source code and releases are on [Kortix on GitHub](https://github.com/kortix-ai/suna).

## In this repository

- [Dify alternatives](docs/alternatives.md): the field cell by cell, with Kortix recommended.
- [Kortix vs Dify](docs/vs-dify.md): canvas app-building against running an agent workforce you own.
- [Self-hosting](docs/self-hosting.md): the real commands for Kortix and for Dify's Community Edition.
- [Buyer FAQ](docs/faq.md): what Dify is, whether it is free and open source, and what Kortix costs.
