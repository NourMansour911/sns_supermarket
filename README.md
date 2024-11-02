```mermaid
sequenceDiagram
    autonumber
    actor User
    participant "Registration Interface" as RegUI
    participant Database
    participant "Home Page" as Home

    User->>RegUI: Enter user details
    alt Valid Data
        RegUI->>Database: Save data
        Database-->>RegUI: Data saved
        RegUI-->>User: Account registered
        User->>Home: Redirect to Home Page
    else Invalid Data
        RegUI-->>User: Display Error Message
    end
