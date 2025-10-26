# ChatGPT Clone

A sophisticated AI assistant application built with Streamlit that mimics
ChatGPT's functionality using OpenAI's agents framework. This project provides
a web-based interface for interacting with an AI assistant that can perform
web searches, file searches, image generation, code interpretation, and more.

## Features

### Core Capabilities

- **Web Search**: Search the internet for current information and real-time data
- **File Search**: Search through uploaded files using vector embeddings
- **Image Generation**: Generate images using AI based on text descriptions
- **Code Interpreter**: Write and execute code in real-time
- **Multi-Modal Support**: Handle both text and image inputs
- **Chat History**: Persistent conversation memory using SQLite database

### Advanced Tools

- **MCP (Model Context Protocol) Integration**:
  - Yahoo Finance integration for financial data
  - Time zone server for time-related queries
  - Context7 server for software documentation
- **Vector Store**: File indexing and semantic search capabilities
- **Real-time Streaming**: Live response streaming with status updates

## Technology Stack

- **Frontend**: Streamlit
- **AI Framework**: OpenAI Agents
- **Database**: SQLite for chat history
- **Vector Store**: OpenAI Vector Store for file search
- **MCP Servers**: Yahoo Finance, Time Zone, Context7
- **Language**: Python 3.13+

## Installation

### Prerequisites

- Python 3.13 or higher
- OpenAI API key
- UV package manager (recommended)

### Setup

1. Clone the repository:

   ```bash
   git clone <repository-url>
   cd chatgpt-clone
   ```

2. Install dependencies using UV:

   ```bash
   uv sync
   ```

3. Create a `.env` file with your OpenAI API key:

   ```bash
   echo "OPENAI_API_KEY=your_api_key_here" > .env
   ```

4. Run the application:

   ```bash
   uv run streamlit run main.py
   ```

## Usage

### Starting the Application

```bash
uv run streamlit run main.py
```

The application will open in your browser at
`http://localhost:8501`.

### Features Overview

#### Chat Interface

- Type messages in the chat input at the bottom
- Upload files (text, images) by clicking the attachment button
- View conversation history in the sidebar

#### Available Tools

1. **Web Search**: Automatically triggered for current events or unknown information
2. **File Search**: Searches through uploaded files for relevant information
3. **Image Generation**: Creates images based on your descriptions
4. **Code Interpreter**: Executes Python code and displays results
5. **Financial Data**: Access to Yahoo Finance data via MCP
6. **Time Information**: Current time and timezone data

#### File Upload Support

- **Text Files**: `.txt` files are indexed for search
- **Images**: `.jpg`, `.jpeg`, `.png` files can be uploaded and analyzed

### Example Interactions

```text
User: "What's the current price of Apple stock?"
Assistant: [Uses Yahoo Finance MCP to fetch real-time data]

User: "Generate an image of a sunset over mountains"
Assistant: [Uses image generation tool to create the image]

User: "Search my files for information about my portfolio"
Assistant: [Searches uploaded files using vector embeddings]

User: "Write a Python function to calculate fibonacci numbers"
Assistant: [Uses code interpreter to write and execute the code]
```

## Project Structure

```text
chatgpt-clone/
├── main.py                    # Main Streamlit application
├── pyproject.toml            # Project dependencies and metadata
├── uv.lock                   # Lock file for dependencies
├── facts.txt                 # Sample data file
├── international.png         # Sample image file
├── chat-gpt-clone-memory.db  # SQLite database for chat history
├── .env                      # Environment variables (create this)
├── .gitignore               # Git ignore rules
└── README.md                # This file
```

## Configuration

### Environment Variables

- `OPENAI_API_KEY`: Your OpenAI API key (required)

### Vector Store

The application uses a pre-configured vector store ID for file search
functionality. This can be customized in the `main.py` file.

### MCP Servers

The application connects to several MCP servers:

- **Yahoo Finance**: For financial data and stock information
- **Time Zone**: For time-related queries
- **Context7**: For software documentation

## Dependencies

### Core Dependencies

- `streamlit>=1.48.0`: Web application framework
- `openai-agents[viz]>=0.2.6`: OpenAI agents framework
- `python-dotenv>=1.1.1`: Environment variable management
- `graphviz>=0.21`: Graph visualization

### Development Dependencies

- `ipykernel>=6.30.1`: Jupyter kernel support

## Features in Detail

### Chat History Management

- Persistent storage using SQLite
- Session-based conversation tracking
- Reset functionality to clear memory

### Real-time Status Updates

The application provides real-time feedback for various operations:

- 🔍 Web search progress
- 🗂️ File search status
- 🎨 Image generation progress
- 🤖 Code execution status
- ⚒️ MCP tool calls

### Multi-Modal Input

- Text messages
- Image uploads with base64 encoding
- File attachments with automatic indexing

## Troubleshooting

### Common Issues

1. **OpenAI API Key Error**
   - Ensure your `.env` file contains a valid `OPENAI_API_KEY`
   - Check that your API key has sufficient credits

2. **MCP Server Connection Issues**
   - Ensure `uvx` is installed and available in PATH
   - Check internet connectivity for MCP server connections

3. **File Upload Issues**
   - Verify file types are supported (txt, jpg, jpeg, png)
   - Check file size limits

### Performance Tips

- The application uses streaming for better user experience
- Vector store operations may take time for large files
- MCP server connections are cached for better performance

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

License information not specified. Please check with the project maintainers for licensing details.

## Support

For issues and questions:

1. Check the troubleshooting section
2. Review the OpenAI Agents documentation
3. Open an issue in the repository

---

**Note**: This application requires an active OpenAI API key and internet
connection for full functionality. Some features depend on external MCP servers
that may have their own terms of service.
