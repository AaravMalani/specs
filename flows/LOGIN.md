# Login Flows

## Flowchart
```mermaid
flowchart TD

    A[Page opens] --> B{Is the user logged in?}

    B -->|Yes| C([Go to the home page])

    B -->|No| K{Does the user have a valid passkey?}

    K -->|Yes| L[Ask the user whether they want to sign in with the passkey]

    K -->|No| D[Display the login form]

    L -->|User clicks no| D

    L -->|User clicks yes| C

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