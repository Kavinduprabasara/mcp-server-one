# Weather Server (MCP)

A minimal async Python server that provides weather alerts and forecasts for US locations using the National Weather Service (NWS) API, built with FastMCP.

## Features

- **Get weather alerts** for any US state (by two-letter code)
- **Get weather forecasts** for any latitude/longitude in the US
- Simple, async, and easy to extend

## Requirements

- Python 3.13+
- [httpx](https://www.python-httpx.org/)
- [mcp](https://pypi.org/project/mcp/) (and FastMCP)
- [uv](https://github.com/astral-sh/uv) (for running the server, optional)

## Installation

1. Clone this repository:
    ```sh
    git clone <your-repo-url>
    cd mcp-server-one
    ```

2. Install dependencies:
    ```sh
    pip install -e .
    ```

## Usage

You can run the server using the provided configuration (see `mcp.json`):

```sh
uv run --with mcp[cli] mcp run server.py
```

Or, directly with Python:

```sh
python server.py
```

## API Tools

### Get Weather Alerts

- **Function:** `get_alerts(state: str)`
- **Description:** Returns active weather alerts for a US state (e.g., `CA`, `NY`).

### Get Weather Forecast

- **Function:** `get_forecast(latitude: float, longitude: float)`
- **Description:** Returns the weather forecast for the given coordinates.

## Project Structure

```
server.py         # Main server code
pyproject.toml    # Project metadata and dependencies
mcp.json          # (Optional) MCP/uv run configuration
README.md         # This file
```