
<img src="https://github.com/user-attachments/assets/b69e5f17-1e50-41e5-8771-be6a84daa750" width="48" height="48"/>

# Claude Server

### THIS PROJECT IS A PART OF [Zolve Extension](https://github.com/gitnasr/zolve)

Claude Server is a Python-based API server that integrates with the Claude API. It provides endpoints to send messages and create new chat sessions with support for file attachments.

[![Build and Deploy Claude Server](https://github.com/gitnasr/claude-engine/actions/workflows/build.yml/badge.svg)](https://github.com/gitnasr/claude-engine/actions/workflows/build.yml)


## Project Structure

- **`app.py`**  
  Contains the `ServerAPI` and `ClaudeServer` classes, which implement the FastAPI server and handle API endpoints.
  
- **`claude_api.py`**  
  Implements the `Client` class and supporting methods to interact with the Claude API. It includes functionality for sending messages, creating new chats, and uploading attachments.

- **`main.py`**  
  The entry point for the application. It checks for updates by comparing the current version from `version.py` with the latest release fetched from GitHub. If an update is found, it notifies the user; otherwise, it starts the FastAPI server via the `ServerAPI` class.

- **`version.py`**  
  Contains a single variable that holds the current version of Claude Server.

- **`requirements.txt`**  
  Lists the Python dependencies required to run the project.

- **`assets/`**  
  Contains assets like the project icon used during the build process.

---

## Project Flow

### 1. Version Check and Startup (`main.py`)
- The application fetches release information from GitHub.
- It compares the latest release version with the current version defined in `version.py`.
- If an update is detected, the user is prompted to update; otherwise, the API server starts using the `ServerAPI` class.

### 2. API Server Endpoints (`app.py`)
- **`POST /claude`**  
  Receives a JSON payload with a list of messages and a conversation ID. It processes each message by sending it to the Claude API using the `ClaudeServer.send_message` method.

- **`POST /claude/new_chat`**  
  Accepts a system prompt to initialize a new chat session. It returns the conversation ID of the newly created chat using the `ClaudeServer.create_new_chat` method.

### 3. Communication with Claude API (`claude_api.py`)
- The `Client` class handles all HTTP requests to the Claude API.
- It includes methods to get organization details, send messages, upload attachments, list conversations, and manage chat sessions.


## Usage

### 1. Download the Latest Version for Windows
- Download the latest version from [here](https://github.com/gitnasr/claude-engine/releases/latest).

### 2. Running the Application Locally (Any other OS)
- Clone this repository.
- Ensure all dependencies listed in `requirements.txt` are installed.
- Run the server using:
  ```sh
  python main.py
  ```

### 3. Accessing the API
- The API endpoints are accessible at:
  - `POST /claude`: Send a message to an existing conversation.
  - `POST /claude/new_chat`: Create a new chat session with a system prompt.

---

## Contributing

### How to Contribute
We welcome contributions from the community! To contribute:

1. **Fork the Repository**  
   Click the "Fork" button at the top right of this repository to create a personal copy.

2. **Clone the Repository**  
   ```sh
   git clone https://github.com/gitnasr/claude-engine
   cd claude-engine
   ```

3. **Create a Feature Branch**  
   ```sh
   git checkout -b feature-branch-name
   ```

4. **Make Changes & Commit**  
   ```sh
   git add .
   git commit -m "Description of changes"
   ```

5. **Push Changes to GitHub**  
   ```sh
   git push origin feature-branch-name
   ```

6. **Create a Pull Request**  
   Navigate to your repository on GitHub, click "Compare & pull request," and submit your changes for review.

### Guidelines
- Write clear and concise commit messages.
- Include documentation for new features.
- Test your changes before submitting.



