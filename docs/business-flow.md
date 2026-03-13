
```mermaid
sequenceDiagram
    participant Operator
    participant AdminWeb
    participant Interface
    participant GameServer
    participant GameDB

    Operator->>AdminWeb: Request item grant
    AdminWeb->>Interface: API request
    Interface->>GameServer: Command request
    GameServer->>GameDB: Update item data
    GameDB-->>GameServer: Success
    GameServer-->>Interface: Result
    Interface-->>AdminWeb: Response
