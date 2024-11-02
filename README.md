
### 2. **Login Process Activity Diagram**

```markdown
```mermaid
flowchart TD
    A[Start] --> B[Enter Email and Password]
    B --> C[Check Email and Password in Database]
    C --> D{Does User Exist?}
    D -- Yes --> E[Are Email and Password Valid?]
    E -- Yes --> F[Redirect to Home Page]
    E -- No --> G[Display Error Message]
    D -- No --> G
    F --> H[End]
    G --> B
