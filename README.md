graph TD
    A[User clicks "Forgot Password"] --> B[Redirect to Email Entry Page]
    B --> C[User enters email]
    C --> D[Check email in database]
    D -->|Valid email| E[Send code via email]
    D -->|Invalid email| F[Display error: User does not exist]
    E --> G[User enters code]
    G -->|Correct code| H[Enter new password twice]
    H --> I[Save new password]
    I --> J[Redirect to Login Page]
    G -->|Wrong code| K[Display error: Wrong code]
    K --> G
    F --> B
