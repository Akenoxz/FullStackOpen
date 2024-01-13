sequenceDiagram
    participant User
    participant Browser
    participant Server

    Note left of User: User writes a note and clicks 'Save'

    User->>Browser: Input new note
    activate Browser

    Browser->>Server: POST https://studies.cs.helsinki.fi/exampleapp/spa/new_note
    activate Server
    Note over Server: Server processes the new note
    Server-->>Browser: Response (Success or Error Message)
    deactivate Server

    Note right of Browser: If success, JavaScript updates the SPA view with the new note
    deactivate Browser
