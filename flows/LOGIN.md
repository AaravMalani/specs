# Login Flows

The login process checks 
- whether the user is logged in
- whether the user authorised a valid passkey
- whether the user enters a valid credential pair (and if they enter their 2FA code correctly)
- whether the user has a valid account via SSO (and if they enter their 2FA code correctly)

If any of these conditions are satisfied, the user is logged in.

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

    D -->|User clicks Google SSO button| M[Go to Google's sign in page]

    M -->|User signs in with their Google account| N[Go to Google SSO redirect URI]
    
    N --> O{Does the user have a valid account?}
    
    O -->|Yes| H
    
    O -->|No| P([Go to Google SSO handler for the registration page])
```

## Limitations
- Only covers Google SSO, since other providers have a similar user flow.
- The login flow doesn't consider multiple incorrect credential attempts.
- The flow does not include an option for a forgotten password.
- The flow does not redirect users back to the page where they came from, instead opting to redirect them to the home page.