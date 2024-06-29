# Exercise 0.6: New note in Single page app diagram
``` mermaid
sequenceDiagram

  actor User
  participant Browser
  participant Server

  User ->> Browser: User types note and clicks 'Save'
  note over Browser: Browser executes event handler that<br/>runs redrawNotes and renders notes
  Browser -->> User: Displays updated web page
  note over Browser: Note is formatted as json and sent<br/>{content: "Frenzal Rhomb swear too much", date: "2024-06-29T06:23:53.706Z"}
  Browser ->> Server: HTTP POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
  Server -->> Browser: HTTP Status code 201 Created


  note over User: User reads new note and nods head in agreement

```
