# 💬 Chat App — Real-Time Multi-Client Messaging

A full-featured real-time chat application built with Python sockets, supporting **text messaging**, **file sharing**, and a **graphical user interface**.

[![Python](https://img.shields.io/badge/Python-3.10-blue)](https://python.org)
[![Tkinter](https://img.shields.io/badge/GUI-Tkinter-green)](https://docs.python.org/3/library/tkinter.html)
[![Sockets](https://img.shields.io/badge/Networking-Sockets-orange)]()
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)
[![CI](https://github.com/abdallahakram20/Chat-App/actions/workflows/ci.yml/badge.svg)](https://github.com/abdallahakram20/Chat-App/actions)

---

## ✨ Features

- 💬 **Real-time text messaging** between multiple clients
- 📁 **File sharing** — send any file type (images, videos, documents)
- 🖼️ **Inline image preview** — images display directly in the chat window
- 🗜️ **Data compression** using zlib for faster transfers
- 👥 **Multi-client support** with username system
- 🖥️ **Tkinter GUI** — clean graphical interface
- ☁️ **Deployed on Railway** — accessible from anywhere

---

## 🏗️ Architecture

```
┌─────────────┐        TCP Socket        ┌─────────────┐
│  Client 1   │ ◄──────────────────────► │             │
├─────────────┤                          │   Server    │
│  Client 2   │ ◄──────────────────────► │  (Railway)  │
├─────────────┤    JSON Header + zlib    │             │
│  Client N   │ ◄──────────────────────► │             │
└─────────────┘                          └─────────────┘
```

**Packet Structure:**
- 4-byte header length (big-endian)
- JSON header `{type, length, meta}`
- zlib-compressed payload

---

## 🛠️ Tech Stack

| Component | Technology |
|-----------|-----------|
| Language | Python 3.x |
| Networking | TCP Sockets + Threading |
| GUI | Tkinter + ScrolledText + PIL |
| Compression | zlib |
| Deployment | Railway |
| Notebook | Jupyter (Client.ipynb / Server.ipynb) |

---

## 📦 Installation

```bash
# Clone the repository
git clone https://github.com/abdallahakram20/Chat-App.git
cd Chat-App

# Install dependencies
pip install -r requirements.txt
```

## 🚀 Usage

### Run locally

```bash
# Terminal 1 — Start the server
python server.py

# Terminal 2+ — Start client(s)
python client.py
```

### Use hosted server (Railway)
The server is deployed on Railway. Just run the client:
```bash
python client.py
```

---

## 📁 Project Structure

```
Chat-App/
├── server.py              # Multi-threaded TCP server
├── client.py              # GUI client (Tkinter + PIL)
├── client1.py             # Alternative client version
├── Client.ipynb           # Jupyter notebook — client demo
├── Server.ipynb           # Jupyter notebook — server demo
├── client_received_files/ # Auto-saved received files
├── requirements.txt
└── README.md
```

---

## 🤝 Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## 📄 License

MIT License — see [LICENSE](LICENSE) for details.
