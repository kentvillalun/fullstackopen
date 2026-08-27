sequenceDiagram
    participant browser
    participant server

    Note right of browser: user types a note and clicks Save
    Note right of browser: spa.js prevents the default form submit
    Note right of browser: browser adds the note to the page immediately using the DOM API

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    activate server
    Note right of server: server saves the new note
    server-->>browser: 201 Created
    deactivate server

    Note right of browser: no redirect, no reload, no further requests