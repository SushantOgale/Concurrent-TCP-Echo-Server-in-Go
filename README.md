# Concurrent TCP Echo Server in Go

[![Go Report Card](https://goreportcard.com/badge/github.com/SushantOgale/Concurrent-TCP-Echo-Server-in-Go)](https://goreportcard.com/report/github.com/SushantOgale/Concurrent-TCP-Echo-Server-in-Go)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A high-performance, concurrent TCP server implemented in Go. This project demonstrates advanced network programming concepts, specifically focusing on how Go’s concurrency model can be used to manage multiple simultaneous client connections efficiently.

##  Why This Project?

Traditional "sequential" servers can only handle one client at a time; others must wait in a queue. This server utilizes **Goroutines**, allowing it to:
* **Scale Dynamically:** Each connection is handled in its own lightweight thread.
* **Low Overhead:** Uses minimal CPU and RAM compared to thread-per-connection models in C or Java.
* **Efficient I/O:** Implements buffered reading to handle high-frequency data streams without bottlenecking the system.

---

##  Features

* **Concurrent Architecture:** Uses the `go` keyword to spawn independent handlers for every incoming connection.
* **Buffered Processing:** Uses `bufio.NewReader` with a **4KB buffer** to optimize read operations.
* **Detailed Logging:** Tracks client IP addresses, ports, connection status, and data payload in real-time.
* **Robust Error Handling:** Correctly identifies and manages `EOF` (graceful exit), timeouts, and unexpected network interruptions.

---

##  Getting Started

### Prerequisites
* **Go:** version 1.21 or higher installed on your machine.

### Installation & Running
1. **Clone the repository:**
   ```bash
   git clone https://github.com/SushantOgale/Concurrent-TCP-Echo-Server-in-Go.git
   cd Concurrent-TCP-Echo-Server-in-Go
   ```
2. **Initialize the module:**
   ```bash
   go mod init github.com/SushantOgale/Concurrent-TCP-Echo-Server-in-Go
   ```
3. **Start the server:**
   ```bash
   go run main.go
   ```

---

## 🔍 How to Test

Once the server is running on `localhost:3000`, you can connect to it using **Netcat** (`nc`) or **Telnet** from another terminal window.

```bash
# Connect to the server
nc localhost 3000

# Type a message and hit Enter
> Hello from the client!
```

**Server Output Example:**
```text
2026/05/04 21:12:00 listening on localhost:3000
2026/05/04 21:12:05 connected: 127.0.0.1:54321
[127.0.0.1:54321] message: "Hello from the client!"
```

---

## Project Structure

| File | Description |
| :--- | :--- |
| `main.go` | The core server logic, listener, and concurrent handler. |
| `go.mod` | Defines the module path and Go version. |
| `LICENSE` | MIT License details. |
| `README.md` | Project documentation and usage guide. |

---

## 📝 License

Distributed under the **MIT License**. See `LICENSE` for more information.
Is the code running exactly how you want it on your local machine?
