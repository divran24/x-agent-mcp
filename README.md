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

## Prerequisites

- [Node.js](https://nodejs.org/) (version 16 or higher recommended)
- Twitter Developer account and API credentials:
  - `TWITTER_API_KEY`
  - `TWITTER_API_SECRET`
  - `TWITTER_ACCESS_TOKEN`
  - `TWITTER_ACCESS_TOKEN_SECRET`
- Google Gemini API key:
  - `GEMINI_API_KEY`
 
### Server

1. Navigate to the `server` directory:

   ```bash
   cd server
   ```

2. Install dependencies:

   ```bash
   npm install
   ```

3. Create a `.env` file in the `server` directory with your Twitter API credentials:

   ```
   TWITTER_API_KEY=your_api_key
   TWITTER_API_SECRET=your_api_secret
   TWITTER_ACCESS_TOKEN=your_access_token
   TWITTER_ACCESS_TOKEN_SECRET=your_access_secret
   ```

4. Start the server:

   ```bash
   node server.js
   ```

   The server will start and listen on [http://localhost:3001](http://localhost:3001).

### Client

1. Open a new terminal and navigate to the `client` directory:

   ```bash
   cd client
   ```

2. Install dependencies:

   ```bash
   npm install
   ```

3. Create a `.env` file in the `client` directory with your Google Gemini API key:

   ```
   GEMINI_API_KEY=your_gemini_api_key
   ```

4. Run the client:

   ```bash
   node index.js
   ```

5. Interact with the AI in the terminal. You can ask questions or request actions like adding numbers or posting a tweet.

## Notes

- The client and server communicate over SSE, so ensure the server is running before starting the client.
- The Twitter posting tool requires valid Twitter API credentials and appropriate permissions.
- The AI uses Google Gemini to generate responses and decide when to call server tools.
- This project is a demonstration of integrating AI with custom tools in a client-server architecture.

## License

This project is provided as-is under the MIT License.


