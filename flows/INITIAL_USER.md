# Initial User Flows

## Flowcharts
### Main App Flow
```mermaid
flowchart TD

    A[App opens] --> B{Did a valid session persist over app installations?}

    B -->|Yes| C([Go to the home page])

    B -->|No| D[Show a language dropdown]
    
    D --> E([Go to the login page])
```

## Limitations
