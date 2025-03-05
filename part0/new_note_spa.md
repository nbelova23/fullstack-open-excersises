```mermaid
sequenceDiagram
    participant Browser
    participant Server

    Browser-->>Server: GET /spa
    Server-->>Browser: HTML page (spa.html)

    Browser->>Server: GET /main.cs
    Server-->>Browser: CSS file

    Browser->>Server: GET /spa.js
    Server-->>Browser: JavaScript file

    Browser->>Server: GET /data.json
    Server-->>Browser: JSON data (existing notes)

    Note right of Browser: User writes a new note

    Browser->>Server: POST /new_note_spa (JSON data)
    Server-->>Browser: 201 created (no redirect)

    Note right of Browser: Page does not reload, new note appears dynamically