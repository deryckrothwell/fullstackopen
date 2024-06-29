# Exercise 0.4 - New note diagram

```mermaid
sequenceDiagram

  actor User
  participant Browser
  participant Server

  User ->> Browser: Writes note in text field and clicks 'Save'
  Browser ->> Server: HTTP POST https://studies.cs.helsinki.fi/exampleapp/new_note
  Server -->> Browser: HTTP status code 302 - URL redirect to location /notes
  Browser ->> Server: GET https://studies.cs.helsinki.fi/exampleapp/notes
  Server -->> Browser: HTML document
  Browser ->> Server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
  Server -->> Browser: CSS file
  Browser ->> Server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
  Server -->> Browser: JavaScript file
  Note over Browser: The browser starts executing the JavaScript code that fetches the JSON from the server
  Browser ->> Server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
  Server -->> Browser: [{ "content": "Frenzal Rhomb is a great band", "date": "2024-06-29T03:51:56.546Z" }, ... ]
  Note over Browser: The browser executes the callback function that renders the notes to the display
  Browser -->> User: Displays page to user
  Note over User: The user scoffs at such a preposterous note

```
