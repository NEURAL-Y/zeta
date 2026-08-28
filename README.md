<div align="center">

<img src="https://raw.githubusercontent.com/NEURAL-Y/zeta/main/public/logo.png" alt="Zeta" width="220"/>

# 🌍 Zeta

**When centralized communication dies, people shouldn't.**

![Status](https://img.shields.io/badge/status-under%20development-yellow)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](#contributing)

[Story](#-story) • [Features](#-features) • [How It Works](#-how-it-works) • [Network Architecture](#-network-architecture) • [Status](#-current-status) • [Roadmap](#-future-roadmap)

</div>

---

Zeta is a decentralized peer-to-peer communication platform built for disaster scenarios where traditional communication infrastructure no longer exists. Instead of relying on cloud servers, every device talks directly to nearby devices over local networks.

## 📖 Story

Humanity's first contact with extraterrestrial life didn't begin with war. It began with silence.

Within hours of arrival, every major communication system collapsed — internet, messaging platforms, phone networks, cloud infrastructure, all unusable. Communities were isolated. Emergency responders couldn't coordinate. Families couldn't reach each other.

Zeta rebuilds communication from the ground up by removing the dependency on centralized infrastructure. Every device becomes an independent node, capable of sending and receiving messages directly.

## ✨ Features

- ⚡ Fully decentralized architecture
- 🤝 Peer-to-peer communication
- 🌐 Local WiFi / mobile hotspot support, internet independent
- 🔄 Automatic reconnection
- 💾 Local message storage (SQLite)
- 🔒 End-to-end encryption *(planned)*
- 📍 Automatic peer discovery *(planned)*
- 📁 File sharing *(planned)*
- 📢 Emergency broadcast *(planned)*
- 📲 Bluetooth fallback *(planned)*

## 🚀 How It Works

```text
Traditional            Zeta
─────────────          ─────────────
User                   Device
  │                       │
Cloud Server         Direct TCP
  │                       │
User                   Device
```

No cloud. No central server. No internet dependency. Each node independently sends and receives messages — every device acts as both **client and server**:

```text
          Local WiFi / Mobile Hotspot

┌──────────────┐                 ┌──────────────┐
│    Phone     │◄───────────────►│    Laptop    │
│ Sender       │                 │ Sender       │
│ Receiver     │                 │ Receiver     │
│ SQLite       │                 │ SQLite       │
└──────────────┘                 └──────────────┘
```

## 🛡 Why Peer-to-Peer?

Most platforms depend on a central server — if it fails, communication stops. Zeta removes that single point of failure: every device is equal, and every device can communicate directly.

## 🌐 Network Architecture

Zeta uses a **hybrid** model. When two devices are in direct range, they connect via **peer-to-peer (P2P)** over local WiFi or a hotspot:

```text
Phone ◄──────────────► Laptop
```

When the destination is out of range, Zeta falls back to a **mesh topology** — intermediate devices relay messages until they reach their target, each acting as both endpoint and relay:

```text
Alice → Bob → Charlie → David
```

| Mode | Used when | Characteristics |
|---|---|---|
| **Direct** | Destination is reachable | Low latency, high bandwidth, no intermediate nodes |
| **Mesh** | Destination is out of range | Forwarded through nearby trusted devices; relays don't need message contents when E2E encryption is enabled |

```text
Destination Reachable?
        │
   ┌────┴────┐
  Yes        No
   │         │
Direct P2P   Mesh Routing
```

## 🔧 Technology Stack

| Component | Technology |
|---|---|
| Language | Python |
| Networking | TCP Sockets |
| Concurrency | asyncio / Threads |
| Storage | SQLite |
| Data Format | JSON |
| Mobile & Desktop | Python |

## 📂 Project Structure

```text
zeta/
├── desktop/    sender.py · receiver.py · network.py · app.py
├── mobile/     sender.py · receiver.py · app.py
├── database/   chat.db
├── shared/     protocol.py · encryption.py · models.py
├── assets/
└── requirements.txt
```

**Message flow:** write → serialize (JSON) → TCP socket → nearby device → deserialize → display.

## 🎯 Current Status

- ✅ Direct peer-to-peer messaging
- ✅ Local network communication
- ✅ Message synchronization & local storage
- ⏳ End-to-end encryption
- ⏳ Bluetooth fallback
- ⏳ Automatic peer discovery
- ⏳ File sharing, voice communication
- ⏳ Mesh networking

## 🌎 Future Roadmap

Mesh networking · delay-tolerant networking (DTN) · multi-hop routing · automatic peer discovery · end-to-end encryption · offline synchronization · emergency broadcast · voice communication · file sharing · community communication networks

## 💡 Vision

In a world where centralized infrastructure can fail, communication shouldn't. Zeta turns every nearby device into an independent communication node — resilient, decentralized communication even when the internet is gone.

## Contributing

Contributions are welcome — bug fixes, docs, protocol work, or new relay/transport support.

1. Fork the repo and branch from `main`.
2. Make focused commits; add tests where relevant.
3. Open a PR describing the change and motivation.

## 📄 License

Released under the [MIT License](LICENSE).

---

<div align="center">

**"Every device is a node. Every connection matters."**

</div>
