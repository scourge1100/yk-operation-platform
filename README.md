# YK Operation Platform

🇰🇷 Korean version: [README.ko.md](README.ko.md)

---

A backend-driven operations platform designed to manage live MMORPG services in a **restricted network environment**, where direct access to game servers is not allowed.

This system was built to solve a critical operational challenge:
how to securely perform real-time game operations without exposing internal servers.

---

## Problem

Game servers were deployed in a fully isolated network for security reasons.
As a result:

* Operators could not directly access game servers
* All operational tasks required a secure mediation layer
* Real-time actions (item distribution, announcements, user management) needed to be reliable and traceable

---

## Solution

Designed a **3-tier architecture with an interface server** acting as a secure gateway between the admin platform and game servers.

* All requests from the admin UI are routed through the interface server
* The interface server validates, transforms, and forwards requests to game servers
* Direct access to internal systems is completely blocked

This approach ensures both **security isolation** and **operational flexibility**.

---

## Key Design Decisions

### 1. Interface Server Pattern

* Prevent direct exposure of game servers
* Centralize request validation and logging
* Enable future extension to multiple game services

### 2. Multi-Database Strategy

* MariaDB for operational data
* MSSQL for legacy or external system integration

### 3. Operator-Centric Design

* Role-based permission system
* Operation history tracking for auditing
* UI optimized for non-developer operators

---

## Architecture

The platform follows a classic 3-tier architecture:

* Presentation Layer: JSP-based admin UI
* Application Layer: Spring-based backend
* Data Layer: MariaDB / MSSQL

- Interface Server for secure communication

(See: docs/architecture.md)

---

## Tech Stack

Backend

* Java
* Spring Framework (eGovFramework)
* MyBatis

Database

* MariaDB
* MSSQL

Infrastructure

* AWS EC2
* AWS RDS
* AWS S3
* AWS CloudWatch

Frontend

* JSP
* JavaScript
* jQuery

---

## My Role

* Designed overall system architecture
* Implemented backend services using Spring + MyBatis
* Built secure communication flow between admin platform and game servers
* Designed database schema and operational workflows
* Deployed and operated the system on AWS

---

## Impact

* Enabled safe and efficient live operations without exposing internal systems
* Reduced manual operational overhead
* Improved reliability and traceability of game operations

---

## Documentation

Detailed system design and architecture documentation:

* [Project Overview (EN)](docs/project-overview.md)
* [Project Overview (KO)](docs/project-overview.ko.md)
* [System Architecture](docs/architecture.md)
* [Business Flow](docs/business-flow.md)
* [Technical Decisions](docs/technical-decisions.md)
* [My Contributions](docs/my-contributions.md)
* [Troubleshooting](docs/troubleshooting.md)
