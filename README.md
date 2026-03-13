# YK Operation Platform

Architecture and system design documentation for a game operations admin platform developed for the MMORPG **열혈강호 W(The Ruler of The Land W)**.

The game servers were isolated from external networks for security reasons, and all operational requests were routed through an interface server.

---

## Project Overview

A web-based operations management platform designed to support live game service administration.

The platform provides tools for game operators to manage announcements, distribute in-game items, monitor user data, and perform operational tasks without direct server access.

---

## Tech Stack

Backend
- Java
- Spring Framework (eGovFramework)
- MyBatis

Database
- MariaDB
- MSSQL

Infrastructure
- AWS EC2
- AWS RDS
- AWS S3
- AWS CloudWatch

Frontend
- JSP
- JavaScript
- jQuery

---

## Documentation

Detailed system design and architecture documentation:

- [Project Overview (EN)](docs/project-overview.md)
- [Project Overview (KO)](docs/project-overview.ko.md)
- [System Architecture](docs/architecture.md)
- [Business Flow](docs/business-flow.md)
- [Technical Decisions](docs/technical-decisions.md)
- [My Contributions](docs/my-contributions.md)
- [Troubleshooting](docs/troubleshooting.md)

---

## Key Highlights

- Web-based admin platform for live game service operations
- Secure communication with game servers through an interface server
- Multi-database integration (MariaDB + MSSQL)
- Operator permission management and operation logging
- AWS-based 3-tier architecture
