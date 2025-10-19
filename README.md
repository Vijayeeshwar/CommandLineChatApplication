# CommandLineChatApplication

**A simple real-time command-line chat application using Python sockets**

> Lightweight multi-client chat server and client designed for learning socket programming and simple LAN chat usage.
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