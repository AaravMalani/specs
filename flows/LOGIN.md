# Login Flows

## Flowchart
```mermaid
flowchart TD

    A[Page opens] --> B{Is the user logged in?}

    B -->|Yes| C([Go to the home page])

    B -->|No| D[Display the login form]

    D -->|User clicks the login button| E{Is the form data valid?}

    E -->|No| F[Show an error]

    E -->|Yes| H{Does the user have 2FA enabled}

    H -->|Yes| I[Prompt the user for the TOTP code]

    H -->|No| C

    I --> J{Is the code valid?}

    J -->|Yes| C

    J -->|No| I

    F --> D

    D -->|User clicks register| G([Go to register page])
```

## Limitations