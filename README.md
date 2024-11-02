
```mermaid
flowchart TD
    A[Start] --> B[User clicks "Forgot Password"]
    B --> C[Redirect to Email Entry Page]
    C --> D[User enters email]
    D --> E[Check email in database]
    
    E -->|Valid email| F[Send code via email]
    E -->|Invalid email| G[Display error: User does not exist]
    
    F --> H[User enters code]
    H -->|Correct code| I[Enter new password twice]
    H -->|Wrong code| J[Display error: Wrong code]
    
    J --> H
    G --> C
    
    I --> K[Save new password]
    K --> L[Redirect to Login Page]
    L --> M[End]
