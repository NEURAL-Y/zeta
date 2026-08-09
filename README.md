# 🌍 Zeta
<img height=500 width=100% src="https://github.com/NEURAL-Y/zeta/blob/main/public/logo.png"/>
> **When centralized communication dies, people shouldn't.**

Zeta is a decentralized peer-to-peer communication platform designed for disaster scenarios where traditional communication infrastructure no longer exists. Instead of relying on cloud servers, every device communicates directly with nearby devices over local networks.

---

## 📖 Story

Humanity's first contact with extraterrestrial life didn't begin with war.

It began with silence.

Within hours of arriving on Earth, every major communication system collapsed. Internet services, messaging platforms, phone networks, and cloud infrastructure became unusable.

Communities were isolated.

Emergency responders couldn't coordinate.

Families couldn't communicate.

Zeta rebuilds communication from the ground up by removing the dependency on centralized infrastructure. Every device becomes an independent communication node capable of sending and receiving messages directly.

---

# ✨ Features

- ⚡ Fully decentralized architecture
- 🤝 Peer-to-peer communication
- 🌐 Local WiFi / Mobile Hotspot support
- 📶 Internet independent
- 🔄 Automatic reconnection
- 💾 Local message storage
- 🔒 End-to-end encryption *(Planned)*
- 📍 Automatic peer discovery *(Planned)*
- 📁 File sharing *(Planned)*
- 📢 Emergency broadcast *(Planned)*
- 📲 Bluetooth fallback *(Planned)*

---

# 🏗 Architecture

```text
          Local WiFi / Mobile Hotspot

        ┌───────────────────────────────┐
        │                               │
        │                               │
┌──────────────┐                 ┌──────────────┐
│    Phone     │◄──────────────►│    Laptop    │
│              │                 │              │
│ Sender       │                 │ Sender       │
│ Receiver     │                 │ Receiver     │
│ SQLite       │                 │ SQLite       │
└──────────────┘                 └──────────────┘

     Every device acts as both
        Client and Server
```

---

# 🚀 How It Works

Traditional messaging:

```text
User
  │
Cloud Server
  │
User
```

Zeta:

```text
Device
   │
Direct TCP Connection
   │
Device
```

No cloud.

No central server.

No internet dependency.

Each node independently sends and receives messages.

---

# 🔧 Technology Stack

| Component | Technology |
|-----------|------------|
| Language | Python |
| Networking | TCP Sockets |
| Concurrency | asyncio / Threads |
| Storage | SQLite |
| Data Format | JSON |
| Mobile | Python |
| Desktop | Python |

---

# 📂 Project Structure

```text
zeta/

├── desktop/
│   ├── sender.py
│   ├── receiver.py
│   ├── network.py
│   └── app.py
│
├── mobile/
│   ├── sender.py
│   ├── receiver.py
│   └── app.py
│
├── database/
│   └── chat.db
│
├── shared/
│   ├── protocol.py
│   ├── encryption.py
│   └── models.py
│
├── assets/
├── README.md
└── requirements.txt
```

---

# 🔄 Communication Flow

```text
User
 │
 ▼
Write Message
 │
 ▼
Serialize (JSON)
 │
 ▼
TCP Socket
 │
 ▼
Nearby Device
 │
 ▼
Deserialize
 │
 ▼
Display Message
```

---

# 📡 Communication Layers

### Primary Layer

- Local WiFi
- Mobile Hotspot

Provides high-speed communication without internet access.

### Secondary Layer *(Planned)*

- Bluetooth

Automatically used when WiFi or hotspot communication is unavailable.

---

# 🛡 Why Peer-to-Peer?

Most communication platforms rely on centralized infrastructure.

```text
Users
   │
Server
   │
Users
```

If the server fails, communication stops.

Zeta removes this single point of failure.

```text
Phone ◄────────────► Laptop
```

Every device is equal.

Every device can communicate directly.

-# 🌐 Network Architecture

Zeta uses a **hybrid communication architecture**.

When two devices are within direct communication range, they establish a **peer-to-peer (P2P)** connection over a local WiFi network or mobile hotspot.

```
Phone  ◄──────────────►  Laptop
```

However, direct communication is not always possible. If the destination device is outside the communication range, Zeta transitions to a **mesh topology**, where intermediate devices relay encrypted messages until they reach their destination.

```
Alice
   │
   ▼
Bob
   │
   ▼
Charlie
   │
   ▼
David
```

Each device acts as both a communication endpoint and a relay node, extending the effective communication range without requiring centralized infrastructure.

---

## Communication Strategy

### Direct Mode

Used when the destination device is directly reachable.

- Low latency
- High bandwidth
- Point-to-point communication
- No intermediate nodes

```
Sender ─────────► Receiver
```

---

### Mesh Mode

Used when the destination device is outside direct communication range.

Messages are securely forwarded through nearby trusted devices.

```
Sender
   │
Relay Node
   │
Relay Node
   │
Receiver
```

Each relay only forwards packets and does not need to access message contents when end-to-end encryption is enabled.

---

## Communication Priority

```
Destination Reachable?
        │
   ┌────┴────┐
   │         │
  Yes        No
   │         │
Direct P2P   Mesh Routing
```

---

## Future Enhancements

- Automatic peer discovery
- Dynamic route selection
- Multi-hop mesh routing
- Bluetooth relay support
- Delay-Tolerant Networking (DTN)
- Store-and-forward messaging
- End-to-end encrypted message forwarding

# 🎯 Current Status

- ✅ Direct peer-to-peer messaging
- ✅ Local network communication
- ✅ Message synchronization
- ✅ Local message storage
- ⏳ End-to-end encryption
- ⏳ Bluetooth fallback
- ⏳ Automatic peer discovery
- ⏳ File sharing
- ⏳ Voice communication
- ⏳ Mesh networking

---

# 🌎 Future Roadmap

- Mesh Networking
- Delay-Tolerant Networking (DTN)
- Multi-hop Routing
- Automatic Peer Discovery
- End-to-End Encryption
- Offline Synchronization
- Emergency Broadcast
- Voice Communication
- File Sharing
- Community Communication Networks

---

# 💡 Vision

In a world where centralized infrastructure can fail, communication should not.

Zeta transforms every nearby device into an independent communication node, enabling resilient, decentralized communication even when the internet is unavailable.

---

# 📄 License

MIT License

---

> **"Every device is a node. Every connection matters."**
