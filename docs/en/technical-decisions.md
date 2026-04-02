# Technical Decisions

This document describes key architectural and technical decisions used in the system, along with the reasoning behind them.

Although the initial architecture was already defined, I analyzed and understood these design choices while implementing backend features.

---

## Interface Server-Based Architecture

The system uses an Interface Server to handle communication between the admin platform and the game servers.

Due to security constraints, game servers are not directly accessible from external systems.
All operational requests must go through the Interface Server.

This approach provides:

* A single entry point for all external requests
* Centralized validation and control of operations
* Improved security by isolating internal systems

Understanding this structure was essential for implementing stable integrations with external systems.

---

## Secure Communication via Bastion Server

Game servers are located within a private network,
and communication is established through SSH tunneling via a Bastion Server.

This design ensures:

* Controlled access to internal infrastructure
* Prevention of direct exposure of game servers
* Secure handling of sensitive operational requests

---

## Data Access Strategy (Interface-Based Access)

The admin platform directly interacts only with MariaDB for operational data.
Game data stored in MSSQL is not accessed directly, but instead handled through the Interface Server.

This approach has the following characteristics:

* The admin system uses its own database (MariaDB) directly
* Game data is accessed indirectly through the Interface Server
* Data access paths are clearly separated

This design provides:

* Protection of the game database from direct access
* Reduced coupling between systems
* Improved security and data integrity

While implementing features, it was important to understand that data retrieval is performed via API calls rather than direct database queries.

---

## Layered Architecture (Controller / Service / DAO)

The backend follows a layered architecture structure:

* Controller: Handles incoming requests
* Service: Contains business logic
* DAO: Manages database access

This design improves:

* Maintainability
* Separation of concerns
* Reusability of business logic

Following this structure ensured consistency during feature implementation.

---

## Server-Side Rendering (JSP)

The system uses JSP for server-side rendering.

This approach:

* Simplifies integration with backend logic
* Works well in legacy enterprise environments
* Eliminates the need for a separate frontend infrastructure

However, it requires careful handling to avoid tight coupling between the UI and business logic.

---

## Conclusion

Although the architecture was pre-defined,
analyzing and understanding these technical decisions enabled consistent and stable feature implementation.

This experience strengthened my ability to understand system architecture
and apply it effectively during development.
