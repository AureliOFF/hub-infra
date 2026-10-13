# hub-infra

Infrastructure as Code (IaC) for the **Hub** ecosystem.

This repository follows a strict **Issue-Driven Development** approach, structured across 5 core milestones designed for incremental building and hands-on learning.

---

## 📌 Overview

`hub-infra` provides the foundational infrastructure stack for the platform:
- Edge routing and reverse proxy
- Relational persistence with logical database isolation
- Asynchronous messaging and queues
- Centralized Identity and Single Sign-On (SSO)
- Governance, secrets management, and automated backups

---

## 🗺️ Roadmap & Milestones

The infrastructure is implemented progressively following the GitHub issues and milestones:

1. **Milestone 1: Networking & Edge Gateway**
   - Core bridge network topology (`portal_net`)
   - Ingress controller provisioning (Traefik v3)
   - Security headers, BasicAuth middlewares, and operational dashboard
   - Secure edge connectivity via Cloudflare Tunnel (`cloudflared`)

2. **Milestone 2: Persistence & Logical Isolation**
   - PostgreSQL 16 service with named volume persistence
   - Network isolation (Zero Host Port Exposure)
   - Multi-database bootstrap (`init.sql` / `init.sh`) adhering to the Principle of Least Privilege (PoLP)
   - Healthcheck orchestration (`pg_isready`)

3. **Milestone 3: Messaging & Queue Management**
   - RabbitMQ 3.13 broker with network isolation
   - Resource limits (RAM threshold & High Watermark)
   - Management dashboard routing via Traefik
   - Virtual hosts (`portal_vhost`), application users, and Dead Letter Exchange (DLX) policies

4. **Milestone 4: Identity & Single Sign-On**
   - Keycloak deployment in production mode (`start`)
   - Relational database integration with PostgreSQL
   - Ingress routing and strict hostname configuration
   - Multi-tenancy Realm, OIDC clients (SPA & bearer-only APIs), and roles

5. **Milestone 5: Governance, Secrets & CI/CD**
   - 12-Factor parameterization via `.env.example`
   - Daemon log rotation (`json-file`)
   - Automated logical backup routines and retention policies
   - Continuous Integration (CI) and Compose syntax linting

---

## 🚀 Getting Started

Development in this repository is driven step-by-step through GitHub issues.

### Prerequisites

- [Docker](https://docs.docker.com/get-docker/) & [Docker Compose](https://docs.docker.com/compose/)
- [Git](https://git-scm.com/)

### Guided Workflow

1. Select the next open issue from the [GitHub Issues](https://github.com/AureliOFF/hub-infra/issues) backlog.
2. Create or update the specific configuration files required by the issue.
3. Validate changes locally.
4. Commit following [Conventional Commits](https://www.conventionalcommits.org/):
   ```bash
   git commit -m "<type>: <description>"
   ```

---

## 📄 License

Internal infrastructure repository for the Hub platform. All rights reserved.
