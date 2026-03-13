# Data Flow

## User Operation Flow

```mermaid
sequenceDiagram
    participant Operator
    participant AdminUI
    participant API
    participant DB

    Operator->>AdminUI: Request operation data
    AdminUI->>API: REST request
    API->>DB: Query data
    DB-->>API: Result
    API-->>AdminUI: Response
