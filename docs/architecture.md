# System Architecture

This document describes the system architecture of the **Yeolhyeolgangho W Operations Platform**.

---

## Architecture Overview

The operations platform was designed using an **AWS-based 3-Tier Architecture** to support secure and controlled game service operations.

The system separates the administration platform, interface layer, and game servers into different roles to ensure security and operational stability.

Game servers were isolated from external networks, and all operational requests from the admin platform were routed through an **interface server** before reaching the game servers.

---

## Architecture Diagram

```mermaid
graph TD

Operator[Operator - Company Network]

Operator --> AdminWeb[Admin Web Server - Private EC2]

AdminWeb --> AdminDB[(MariaDB - Admin DB)]

AdminWeb --> InterfaceServer[Interface Server - API Gateway]

InterfaceServer --> Bastion[Bastion Server - SSH Tunnel]

Bastion --> GameServer[Game Server Cluster]

GameServer --> GameDB[(MSSQL - Game DB)]
