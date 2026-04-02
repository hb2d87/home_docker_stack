# 🏠 Home Docker Stack (Backup)

This repository serves as a secure, version-controlled backup of the active Docker stacks currently running on this workstation, managed via `DockHand`.

## 🏗️ Active Infrastructure
The configurations in this repository are direct mirrors of the live files located in the DockHand volume:
`/var/lib/docker/volumes/dockhand_dockhand_data/_data/stacks/homelab/`

- **Data Stack:** Central PostgreSQL (pgvector) and local backup automation.
- **AI Stack:** n8n workflow engine and OpenCode web IDE.
- **Utility Stack:** Syncthing (file sync), Filebrowser (remote access), and Silverbullet (knowledge base).

## 🔒 Security & Backup Policy
To ensure this public repository remains safe:
- **Strict Allow-List:** Only `.yml`/`.yaml` files and documentation are tracked.
- **Excluded:** All `.env` files, `.sql` database dumps, and persistent data volumes are ignored by default.
- **Purpose:** This is a reference for infrastructure state, not a "live" deployment repo.

---
*Maintained by hb2d. Mirror of the live DockHand environment on Pop!_OS.*
