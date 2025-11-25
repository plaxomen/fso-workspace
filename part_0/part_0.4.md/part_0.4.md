# 0.4 New Note Diagram

```mermaid
sequenceDiagram
    participant browser
    participant server

    Note over browser: Input New Note

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    activate server
    Note right of browser: payload: {note: ...}


    server-->>browser: 302 Found for Redirect
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server

    server-->>browser: 200 OK (HTML Document)
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server

    server-->>browser: 200 OK (CSS Stylesheet)
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server

    server-->>browser: 200 OK (JavaScript Script)
    deactivate server

    Note over browser: Execute JavaScript

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server

    server-->>browser: 200 OK (JSON Notes Data)
    deactivate server

    Note over browser: Render Notes
```