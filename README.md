# x-agent-mcp

This project demonstrates a simple client-server application using the Model Context Protocol (MCP) SDK. The backend server exposes tools that can be called by the client, which uses AI to interact with these tools in a conversational manner.

## How It Works

- The **server** is an Express application that uses the MCP SDK to define tools. Currently, it provides two tools:
  - `addTwoNumbers`: Adds two numbers and returns the result.
  - `createPost`: Posts a status update to Twitter using the Twitter API.
- The server supports Server-Sent Events (SSE) to handle real-time communication with multiple clients.
- The **client** is a Node.js command-line interface (CLI) application that connects to the server via SSE.
- The client uses Google Gemini AI to generate conversational content and decide when to call server tools.
- Users interact with the client via the terminal, typing messages and receiving AI-generated responses.
- When the AI decides to call a tool, the client sends the request to the server and displays the tool's response.


