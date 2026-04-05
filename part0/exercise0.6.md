# Exercise 0.6: New Note in SPA Diagram

```mermaid
sequenceDiagram
    participant browser
    participant server

    Note over browser: User types note and clicks "Save"
    Note right of browser: The browser's JS code adds the note to the local list and re-renders the UI

    browser->>server: POST [https://studies.cs.helsinki.fi/exampleapp/new_note_spa](https://studies.cs.helsinki.fi/exampleapp/new_note_spa)
    activate server
    Note left of server: Server saves the note JSON sent in the request body
    server-->>browser: 201 Created (JSON: {"message":"note created"})
    deactivate server

    Note right of browser: No further requests are made; the page does not reload
```
