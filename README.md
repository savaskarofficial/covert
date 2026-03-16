<div align="center">

<img src="https://img.shields.io/badge/Covert-HTTP%20Debugger%20%26%20API%20Client-blueviolet?style=for-the-badge&logo=radar&logoColor=white" alt="Covert" />

# Covert

**Advanced HTTP Debugger, MITM Proxy & API Client**

*By [Undercover IT Firm](https://undercoveritfirm.com)*

<img src="https://img.shields.io/badge/Platform-Windows%20%7C%20macOS%20%7C%20Linux%20%7C%20Android%20%7C%20iOS-blue?style=flat-square" />
<img src="https://img.shields.io/badge/Protocols-HTTP%2F1.1%20%7C%20HTTP%2F2%20%7C%20HTTP%2F3-green?style=flat-square" />
<img src="https://img.shields.io/badge/Built%20With-Flutter%20%2B%20C++-02569B?style=flat-square&logo=flutter&logoColor=white" />
<img src="https://img.shields.io/badge/License-Proprietary-red?style=flat-square" />

---

</div>

## Overview

Covert is a next-generation cross-platform HTTP debugging proxy and API testing suite. It combines the power of **Charles Proxy**, **Fiddler**, and **Postman** into a single, high-performance application built with Flutter and C++.

Designed for developers, security researchers, and QA engineers who need deep visibility into HTTP traffic without the complexity of juggling multiple tools.

## Key Features

### 🔍 Traffic Capture & MITM Proxy

- **Full MITM interception** with automatic CA certificate generation and installation
- **HTTP/2 frame-level MITM** — HPACK header decoding, stream multiplexing (not just byte piping)
- **WebSocket frame capture** with real-time display
- Protocol support: HTTP/1.x, HTTP/2, HTTPS (TLS 1.1–1.3), SOCKS4/4a/5
- VPN mode on Android (no Wi-Fi proxy config needed)
- System proxy auto-configuration on Windows, macOS, Linux
- Per-app traffic filtering on Android

### 🛠️ Debugging Tools

- **Rewrite rules** — Redirect, Map Local, Map Remote, header/body modification
- **Breakpoints** — Pause and edit requests/responses in real-time
- **Python scripting** — Custom request/response processing
- **Gateway** — Block, suspend, or throttle specific traffic
- **Mirroring** — Duplicate traffic to a secondary host
- **Network conditions** — Simulate bandwidth limits, latency, packet loss
- **QuickBar** — Reqable-style control center with one-click toggles

### 📡 API Client

- Native **HTTP/1.1, HTTP/2, and HTTP/3 (QUIC)** request support
- **API Collections** with folder organization
- **Environment variables** with `{{variable}}` syntax resolution
- **Pre-request & post-response scripting** (Python/JavaScript DSL)
- Auth: Bearer, Basic, Digest (with 401 auto-retry), NTLM, API Key, OAuth 2.0 (interactive browser flow), AWS SigV4
- Body types: JSON, XML, form-data, multipart, binary upload, GraphQL
- **Code snippets** for 20+ languages (cURL, Python, Java, Go, Kotlin, Swift, C#, PHP, Ruby, Dart, Node.js, and more)
- Import from Postman collections
- Cookie management with auto-save

### 📊 Analysis & Export

- **Response diff viewer** — Side-by-side comparison of any two captured sessions
- **HAR export/import** — Full HTTP Archive format support
- **Repeat & Advanced Repeat** — Replay requests with configurable concurrency and delay
- **Compose** — Open any captured request in the API Client for editing
- **AI Analysis** — Claude-powered request/response analysis

### 🧰 Toolbox

Base64, URL encode/decode, MD5/SHA hash, JSON/XML formatter, JWT decoder, Regex tester, Timestamp converter, HEX viewer, QR code generator, Image viewer

### 🤝 Collaboration

- QR code pairing for mobile ↔ desktop traffic forwarding
- Mock server for local API simulation
- gRPC client with Protobuf support
- Plugin system for extensibility

## Architecture

```
┌──────────────────────────────────────────────────────────────┐
│                        Covert Engine                          │
├──────────────────────────────────────────────────────────────┤
│                                                               │
│  Browser ──TLS──▶ MITM Proxy (SecureServerSocket)            │
│                       │                                       │
│               ALPN negotiation                                │
│               ┌───────┴───────┐                              │
│               │               │                              │
│            h2 ▼            h1.1 ▼                            │
│   ServerTransport      Transparent                           │
│   Connection           Byte Pipe                             │
│    ↕ HPACK decode      + Http1Parser                         │
│    ↕ Stream mux        + WS detection                        │
│   ClientTransport      + Rule evaluation                     │
│   Connection                                                  │
│               │               │                              │
│               ▼               ▼                              │
│  SecureSocket [h2/h1.1] ──TLS──▶ Upstream                   │
│                                                               │
├──────────────────────────────────────────────────────────────┤
│  API Client:  H1 (package:http)                              │
│               H2 (package:http2 — native ALPN)               │
│               H3 (Cronet/QUIC on Android, H2 fallback)       │
├──────────────────────────────────────────────────────────────┤
│  Rule Engine: Gateway │ Rewrite │ Breakpoint │ Script        │
│               Mirror  │ Map Local │ Map Remote │ Highlight   │
│               Throttle │ DNS Override                         │
└──────────────────────────────────────────────────────────────┘
```

## Platform Support

| Platform | Status | Notes |
|----------|--------|-------|
| Windows  | ✅ Stable | System proxy auto-config, emergency cleanup on exit |
| macOS    | ✅ Stable | Network extension for system proxy |
| Linux    | ✅ Stable | gsettings-based proxy configuration |
| Android  | ✅ Stable | VPN mode, per-app filtering, Cronet H3 |
| iOS      | 🚧 Beta | Network extension |

## Comparison

| Feature | Covert | Reqable | Charles | Fiddler | Postman |
|---------|--------|---------|---------|---------|---------|
| HTTP/2 MITM (frame-level) | ✅ | ✅ | ❌ | ❌ | — |
| HTTP/3 API Client | ✅ | ✅ | ❌ | ❌ | ❌ |
| Python Scripting | ✅ | ✅ | ❌ | ✅ | ❌ |
| WebSocket Capture | ✅ | ✅ | ✅ | ✅ | ❌ |
| API Collections | ✅ | ✅ | ❌ | ❌ | ✅ |
| Code Snippets (20+ langs) | ✅ | ✅ | ❌ | ❌ | ✅ |
| Cross-platform (5 OS) | ✅ | ✅ | ❌ | ❌ | ✅ |
| AI Analysis | ✅ | ❌ | ❌ | ❌ | ✅ |
| Free tier | ✅ | ✅ | ❌ | ❌ | ✅ |
| Open telemetry | ✅ | ❌ | ❌ | ❌ | ❌ |

## Download

> Coming soon to Windows, macOS, Linux, Google Play, and the App Store.

## License

Covert is proprietary software developed by Undercover IT Firm.
All rights reserved. © 2024-2026 Undercover IT Firm.

---

<div align="center">

**[Website](https://undercoveritfirm.com)** · **[Telegram](https://t.me/savaskarofficial)** · **[Report Issue](https://github.com/savaskarofficial/covert/issues)**

<sub>Built with precision in Dhaka 🇧🇩</sub>

</div>
