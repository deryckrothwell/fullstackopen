# Exercise 0.5: Single page app diagram
``` mermaid
sequenceDiagram

  actor User
  participant Browser
  participant Server

  User ->> Browser: User clicks on link https://studies.cs.helsinki.fi/exampleapp/spa
  Browser ->> Server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/spa
  Server -->> Browser: HTML document
  Browser ->> Server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.css
  Server -->> Browser: main.css
  Browser ->> Server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/spa.js
  Server -->> Browser: spa.js

  note over Browser: Browser execute spa.js and <br/>requests data.json from server 

  Browser ->> Server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/data.json
  Server -->> Browser: [{content: "Frenzal Rhomb is a great band", date: "2024-06-29T03:51:56.546Z"}, ...]

  note over Browser: Browser executes event handler that <br/>runs redrawNotes and renders notes

  Browser -->> User: Displays web page
  note over User: User marvels at such wondrous notes <br/>left by people from all over the world.

```
