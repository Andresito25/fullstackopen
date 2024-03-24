fetchingNotes

    participant browser
    participant server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa (status code 200)
    activate server
    server->>browser: HTML document
    desactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css (status code 200)
    activate server
    server->>browser: main.css file
    desactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js (status code 200)
    activate server
    server->>browser: spa.js file
    desactivate server

    browser: The spa.js is executing an event listener in the document which execute a callback function that is waiting for any changes to reload the content if find a new note.

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json (status code 200)
    activate server
    server->>browser: JSON file
    desactivate server

    browser: The browser render all the notes
