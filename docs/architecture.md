# System Architecture

## Overview

```mermaid
graph TD

Operator[Game Operator] --> AdminWeb[Admin Web Platform]

AdminWeb --> InterfaceServer[Interface Server]

InterfaceServer --> GameServer[Game Server]

AdminWeb --> AdminDB[(MariaDB)]
GameServer --> GameDB[(MSSQL)]

AdminWeb --> AWS[AWS Infrastructure]
