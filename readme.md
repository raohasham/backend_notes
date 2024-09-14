# Notes API

## Description

This is a simple Express-based REST API for managing notes. It allows you to view all notes, retrieve individual notes by ID, add new notes, and delete notes.

## Features

- **View all notes**: Retrieve a list of all notes.
- **Get note by ID**: Retrieve details of a specific note by its ID.
- **Add a new note**: Add a new note with content and importance status.
- **Delete a note**: Remove a note by its ID.

## Installation

To run this project locally, you'll need to have [Node.js](https://nodejs.org/) installed. Follow these steps:

1. **Clone the repository:**

    ```bash
    git clone https://github.com/raohasham/backend_notes
    cd backend_notes
    ```

2. **Install dependencies:**

    ```bash
    npm install
    ```

3. **Run the application:**

    ```bash
    npm start
    ```

    The application will start and listen on port `3001`.

## Usage

- **Get all notes:**

    ```http
    GET /api/notes
    ```

    This endpoint returns a JSON array of all notes.

- **Get a note by ID:**

    ```http
    GET /api/notes/:id
    ```

    Replace `:id` with the note ID you want to retrieve. This endpoint returns the note details in JSON format.

- **Add a new note:**

    ```http
    POST /api/notes
    ```

    Request body should be a JSON object with the following properties:
    ```json
    {
      "content": "Note content",
      "important": true  // optional, defaults to false if not provided
    }
    ```
    This endpoint adds a new note and returns the created note.

- **Delete a note by ID:**

    ```http
    DELETE /api/notes/:id
    ```

    Replace `:id` with the note ID you want to delete. This endpoint removes the note and returns a 202 Accepted status.

## Endpoints

- **Root endpoint:**

    ```http
    GET /
    ```

    Returns a simple HTML greeting: `<h1>hello world</h1>`.

## Notes

- The application uses in-memory storage for notes, which means that data will be lost when the server restarts.
- The ID for new notes is generated based on the highest existing ID, incremented by 1.

## Troubleshooting

- Ensure that all required fields are included in the request body when adding a new note.
- Check for proper JSON formatting in requests and responses.

