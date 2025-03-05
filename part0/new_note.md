```mermaid
sequenceDiagram
    participant user
    participant browser
    participant server

    user->>browser: Writes note and clicks "Save"
    browser->>server: POST /new_note with note data
    activate server
    server-->>browser: Responds with success
    deactivate server

    Note right of browser: The browser updates the UI with the new note
    browser->>server: Fetch updated note list
    server-->>browser: Sends bacl updated notes