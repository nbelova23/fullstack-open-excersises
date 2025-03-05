```mermaid
sequenceDiagram
    participant browser
    participant server

    browser->>server: GET /spa
    activate server
    server-->browser: HTML document (single-page app)
    deactivate server
   
    browser->>server: GEt /main.css
    activate server
    server-->>browser: CSS file
    deactivate server

    browser->>server: GET /spa.js
    activate server
    server-->>browser: JavaScript file
    deactivate server

    Note right of browser: JavaScript starts running and updates the UI

    browser->>server: GET /data.json
    activate server
    server-->>browser: JSON data with saved notes
    deactivate server

    Note right of browser: Notes are displayed on the page dynamically