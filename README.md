```mermaid
flowchart TD
    A[Start] --> B[Enter User Details]
    B --> C{Is Data Valid?}
    C -- Yes --> D[Save Data to Database]
    D --> E[Account Registered]
    E --> F[Redirect to Home Page]
    C -- No --> G[Display Error Message]
    G --> A
    F --> H[End]
