sequenceDiagram
    participant browser
    participant server

    Note over browser: User clicks button on the form

    browser->>server: POST /new_note with user input
    activate server
    server-->>browser: HTTP 302 Redirect
    deactivate server

    Note over browser: Browser follows the redirect

    browser->>server: GET /notes
    activate server
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET /main.css
    activate server
    server-->>browser: the CSS file
    deactivate server

    browser->>server: GET /main.js
    activate server
    server-->>browser: the JavaScript file
    deactivate server

    browser->>server: GET /data.json
    activate server
    server-->>browser: Raw data of the notes
    deactivate server

    Note over browser: Browser renders the Notes page
