# Rust Webserver

A multi-threaded web server built with Rust, demonstrating core concepts like TCP streams, file I/O, and thread pooling.

## Features

- **Multi-threaded Request Handling**: Efficiently handles multiple concurrent connections using a custom `ThreadPool`.
- **Routing**:
  - `GET /`: Serves the `hello.html` page.
  - `GET /sleep`: Simulates a slow request (5 seconds) to demonstrate non-blocking behavior for other clients.
  - **404 Handling**: Gracefully handles unknown routes by serving a `404.html` page.
- **Clean Architecture**: Separates connection handling and thread management for better code organization.

## Getting Started

### Prerequisites

- [Rust](https://www.rust-lang.org/tools/install) (latest stable version recommended)

### Installation

1.  Clone the repository:
    ```bash
    git clone <repository-url>
    cd webserver
    ```

### Running the Server

Start the server using Cargo:

```bash
cargo run
```

The server will start listening on `127.0.0.1:7878`.

### Usage

1.  Open your web browser.
2.  Navigate to `http://127.0.0.1:7878` to see the welcome page.
3.  Navigate to `http://127.0.0.1:7878/sleep` to test the multi-threaded capabilities. The page will load after 5 seconds, but you can open other tabs to `http://127.0.0.1:7878` immediately without waiting.

## Project Structure

- `src/main.rs`: Entry point. Sets up the TCP listener and handles incoming connections.
- `src/lib.rs`: Contains the `ThreadPool` implementation and worker logic.
- `hello.html`: HTML content for the root route.
- `404.html`: HTML content for 404 errors.

## License

This project is open source and available under the [MIT License](LICENSE).
