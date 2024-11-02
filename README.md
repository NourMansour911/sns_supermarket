```mermaid
sequenceDiagram
    autonumber
    actor User
    participant "Authentication Service" as AuthService
    participant "Database" as DB
    User->>AuthService: Request login
    AuthService->>DB: Verify credentials
    DB-->>AuthService: Send user data
    AuthService-->>User: Login successful
    Note right of User: Display welcome message
    User->>AuthService: Log out
    AuthService-->>User: Confirm log out
