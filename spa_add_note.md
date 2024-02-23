sequenceDiagram
    participant browser
    participant server

    Note over browser: User clicks button on the form

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa with user input
    activate server
    server-->>browser: JSON data of the notes
    deactivate server

    Note over browser: Browser renders the Notes page
