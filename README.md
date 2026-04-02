# 🏠 Home Docker Stack

A modular, multi-stack Docker infrastructure for a high-performance AI automation and personal productivity environment. Managed via `DockHand` on a Pop!_OS workstation.

## 🏗️ Architecture

The infrastructure is split into four logical stacks to maintain clean separation of concerns and data persistence:

- **Data Stack:** Central PostgreSQL database (with `pgvector` for AI) and automated backup rotation.
- **AI Stack:** n8n workflow automation and a web-based VS Code environment.
- **Dify Stack:** LLM application development platform (API, worker, and web UI).
- **Utility Stack:** File synchronization (Syncthing), remote file management (Filebrowser), and networked knowledge base (Silverbullet).

## 🚀 Quick Start

### 1. Prerequisites
- Docker & Docker Compose installed.
- Create the shared backend network:
  ```bash
  docker network create homelab_net
  ```

### 2. Configuration
Copy the template environment file and fill in your secrets:
```bash
cp .env.example .env
# Edit .env with your specific paths and passwords
```

### 3. Deployment
Deploy the stacks in order (starting with Data):
```bash
docker compose -f data-stack/docker-compose.yml up -d
docker compose -f ai-stack/docker-compose.yml up -d
docker compose -f utility-stack/docker-compose.yml up -d
```

## 🔒 Security & Networking

- **Isolation:** Stacks communicate via the internal `homelab_net` to prevent exposing database ports unnecessarily.
- **Access:** Designed to be used with **Tailscale MagicDNS** and **Traefik** for secure, trusted HTTPS without public port exposure.
- **Permissions:** Services are configured to run as PID/GID `1000` to match the host system user for seamless volume permissions.

---
*Maintained by hb2d. Powered by Pop!_OS & COSMIC.*
