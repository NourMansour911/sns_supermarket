```mermaid
sequenceDiagram
    autonumber
    actor User
    participant "Frontend" as FE
    participant "Authentication Service" as AuthService
    participant "Database" as DB
    participant "Logging Service" as LogService

    User->>FE: Initiate Login
    FE->>AuthService: Request Authentication
    alt User credentials valid
        AuthService->>DB: Fetch user data
        DB-->>AuthService: Send user data
        AuthService-->>FE: Authentication successful
        FE-->>User: Login successful
        par 
            FE->>LogService: Log login activity
            FE->>User: Display dashboard
        end
    else User credentials invalid
        AuthService-->>FE: Authentication failed
        FE-->>User: Show error message
    end
    Note right of FE: End of process
