# My Python MCP Server

A Model Context Protocol (MCP) server built with FastMCP that provides useful tools for directory operations and weather information.

## Features

This MCP server provides the following tools:

### 🗣️ `say_hello`
- **Description**: Say hello to someone
- **Parameters**: `name` (string) - The name of the person to greet
- **Returns**: A personalized greeting message

### 📁 `list_directory`
- **Description**: List the contents of a directory
- **Parameters**: `directory_path` (string) - Path to the directory to list
- **Returns**: List of files and folders in the directory
- **Error Handling**: Returns appropriate messages for missing directories or permission issues

### 📋 `list_details`
- **Description**: List directory contents with detailed information
- **Parameters**: `directory_path` (string) - Path to the directory to analyze
- **Returns**: Detailed list including:
  - File/folder name
  - Size in bytes
  - Type (file or directory)
  - Last modified timestamp
- **Error Handling**: Handles missing directories and non-directory paths

### 🌤️ `get_weather`
- **Description**: Fetch current weather information for any city or country
- **Parameters**: `location` (string) - Name of the city or country (e.g., 'Sydney', 'Paris', 'Singapore')
- **Returns**: Plain-text weather summary with temperature and conditions
- **Data Source**: Uses the wttr.in API service
- **Error Handling**: Handles network errors and API failures gracefully

## Requirements

- Python 3.7+
- Required packages:
  - `mcp` - Model Context Protocol library
  - `requests` - For HTTP requests to weather API
  - `pathlib` - For enhanced path operations (built-in)
  - `datetime` - For timestamp formatting (built-in)
  - `os` - For basic file operations (built-in)

## Installation

1. Clone or download this repository
2. Install the required dependencies:
   ```bash
   pip install mcp requests
   ```

## Usage

### Running the Server

To start the MCP server:

```bash
python my_mcp_server.py
```

The server will start and listen for MCP protocol messages via standard I/O.

### Example Tool Usage

Once connected to an MCP client, you can use the tools:

- **Greeting**: `say_hello("Alice")` → Returns: "Hello, Alice! Welcome to MCP."
- **List Files**: `list_directory("C:/Users")` → Returns list of user directories
- **Detailed Listing**: `list_details("./")` → Returns detailed info about current directory contents
- **Weather**: `get_weather("Sydney")` → Returns: "Sydney: ⛅️ +16°C"

## File Structure

```
mcp-exercise/
├── my_mcp_server.py    # Main MCP server implementation
├── README.md           # This documentation file
├── basic_list_dir.py   # (Additional utility file)
└── adv_list_dir.py     # (Additional utility file)
```

## Technical Details

- **Protocol**: Model Context Protocol (MCP)
- **Transport**: Standard I/O (stdio)
- **Framework**: FastMCP for simplified MCP server development
- **Error Handling**: Comprehensive error handling for file operations and network requests
- **Weather API**: wttr.in service for weather data

## Error Handling

The server includes robust error handling:
- File system errors (missing directories, permission issues)
- Network errors for weather requests
- Invalid input validation
- Graceful error messages returned to clients

## Contributing

This is a learning project for MCP server development. Feel free to extend it with additional tools and functionality.

## License

This project is for educational purposes.
