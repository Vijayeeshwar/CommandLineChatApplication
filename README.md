# CommandLineChatApplication

**A simple real-time command-line chat application using Python sockets**

> Lightweight multi-client chat server and client designed for learning socket programming and simple LAN chat usage.

---

## Features

* Server / Client architecture using Python `socket`.
* Simple, text-based command-line interface (no GUI required).
* Supports multiple clients (via threads) connecting to a single server.
* Easy to configure `HOST` and `PORT` in the scripts.

---

## Prerequisites

* Python 3.7 or newer (recommended).
* No external packages required — uses Python standard library (`socket`, `threading`, `sys`).

---

## Repository layout

```
CommandLineChatApp/
├── README.md                 # (this file)
├── server.py                 # Server implementation
├── client.py                 # Client implementation
└── LICENSE (optional)
```

---

## File explanations

### 🖥️ server.py

This file runs the **chat server**. It:

* Creates a socket and binds it to a host (IP address) and port.
* Listens for client connections.
* For each client, starts a new thread to handle messages.
* Broadcasts messages from one client to all other connected clients.
* Manages active clients and removes disconnected ones.

**Main functions:**

* `listen_for_messages(client, username)` — continuously listens for incoming messages from a client and broadcasts them.
* `send_message_to_all(message)` — sends a message to all connected clients.
* `main()` — initializes the server and accepts incoming connections.

### 💬 client.py

This file runs the **chat client**. It:

* Connects to the server via IP and port.
* Asks for a username and sends it to the server.
* Listens for incoming messages from the server in a separate thread.
* Sends user-input messages to the server.

**Main functions:**

* `listen_for_messages_from_server()` — listens for and prints messages sent by the server.
* `send_message_to_server()` — reads input from the user and sends it to the server.
* `main()` — establishes connection and starts both listening and sending threads.

---

## Quick start

1. Clone the repository:

```bash
git clone https://github.com/Chandramalika/CommandLineChatApp.git
cd CommandLineChatApp
```

2. Start the server:

```bash
python server.py
```

3. Start one or more clients:

```bash
python client.py
```

Each client can send and receive messages in real-time.

---

## Configuration

Open `server.py` or `client.py` to edit:

* `HOST` — IP address (`127.0.0.1` for local, or LAN IP for network use)
* `PORT` — TCP port (e.g., `2226`)

---

## Troubleshooting

* **Address already in use** — Change the port or stop other services using the same port.
* **Cannot connect to server** — Ensure correct IP, open firewall port, and same network.

---

## Future Improvements

* Add usernames and message timestamps.
* Encrypt communication using the `ssl` module.
* Add private messaging or GUI using `tkinter`.

---

## License

You can use or modify this project freely under the MIT License.

---

## Author

Developed by **Chandramalika** — a simple learning project for Python socket programming.
