sequenceDiagram
    participant User
    participant Browser
    participant Server

    User->>Browser: Enter URL https://studies.cs.helsinki.fi/exampleapp/spa
    activate Browser

    Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate Server
    Server-->>Browser: SPA HTML document
    deactivate Server

    Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/spa.css
    Server-->>Browser: CSS file

    Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    Server-->>Browser: JavaScript file

    deactivate Browser
    Note right of Browser: Browser renders SPA
    Note right of Browser: JavaScript manages SPA functionality
