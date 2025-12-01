# 0.6: New note in Single page app diagram

```mermaid
sequenceDiagram
    participant browser
    participant server

    Note over browser: Input New Note
    Note over browser: Redraw Notes
    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    Note right of browser: {"content": "...","date": "2025-11-25..."}
    activate server

    server-->>browser: 201 Created
    Note left of server: {"message":"note created"}
    deactivate server

```