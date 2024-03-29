creatingNewNote

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/new_note (status code 302)
    activate server
    server->>browser: HTML document
    desactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes (status code 200)
    activate server
    server->>browser: HTML document
    desactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css (status code 200)
    activate server
    server->>browser: main.css file
    desactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js (status code 200)
    activate server
    server->>browser: main.js file
    desactivate server

    browser: The browser fetch and execute the callback function that creates different nodes in the DOM from the main.js document and list all the notes

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json (status code 200)
    activate server
    server->>browser: JSON file
    desactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json (status code 200)
    activate server
    server->>browser: 92: {content: "Greetings from Colombia, parceros!", date: "2024-03-24T19:04:05.443Z"}
    content:
    "Greetings from Colombia, parceros!"
    date:
    "2024-03-24T19:04:05.443Z"
    desactivate server

    browser: The browser render all the notes even the new note from the JSON file
