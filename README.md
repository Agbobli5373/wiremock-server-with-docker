# WireMock Server with Docker

This project provides a WireMock server setup using Docker, allowing you to easily mock APIs for testing and development purposes.

## Overview

WireMock is a tool for building mock APIs. This project containerizes WireMock using Docker, making it easy to set up and run in any environment.

## Prerequisites

- [Docker](https://www.docker.com/get-started) installed on your machine
- Basic understanding of RESTful APIs and JSON

## Getting Started

### Running the WireMock Server

1. Clone this repository:

   ```
   git clone <repository-url>
   cd wiremock-server-with-docker
   ```

2. Start the Docker container:

   ```
   docker-compose up -d
   ```

3. The WireMock server will be available at `http://localhost:8080`

### Stopping the Server

```
docker-compose down
```

## Project Structure

```
wiremock-server-with-docker/
├── files/             # JSON files for request/response mappings
│   └── file.json      # Sample mapping file
├── docker-compose.yml # Docker Compose configuration
└── README.md          # This file
```

## Configuring Stubs

Create stub mappings in the `files` directory. Each JSON file represents a request/response mapping.

Example mapping:

```json
{
  "request": {
    "method": "GET",
    "url": "/api/example"
  },
  "response": {
    "status": 200,
    "headers": {
      "Content-Type": "application/json"
    },
    "body": "{\"message\": \"This is a mock response\"}"
  }
}
```

## Usage Examples

### Testing with cURL

```bash
# Get a response from the mocked API
curl -X GET http://localhost:8080/api/example
```

### Using with Postman

1. Open Postman and create a new request
2. Set the URL to `http://localhost:8080/api/example`
3. Send the request to receive the mocked response

## Advanced Configuration

For advanced WireMock configurations, refer to the [WireMock Documentation](http://wiremock.org/docs/).

