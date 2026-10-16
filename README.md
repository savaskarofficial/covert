<p align="center">
  <img src="assets/icon/covert_logo_1024.png" alt="Covert Logo" width="180" />
</p>

<h1 align="center">Covert</h1>

<p align="center">
  <strong>Advanced HTTP/HTTPS MITM Proxy, Network Debugger & API Client</strong><br>
  <em>by <a href="https://undercoveritfirm.com">Undercover IT Firm</a> — Sharodshahi Al-Amin</em>
</p>

<p align="center">
  <a href="https://github.com/savaskarofficial/covert/releases/latest"><img src="https://img.shields.io/github/v/release/savaskarofficial/covert?style=flat-square&color=00E5CC&label=Latest%20Release" alt="Release"></a>
  <img src="https://img.shields.io/badge/Platform-Windows%20%7C%20macOS%20%7C%20Linux%20%7C%20Android-blue?style=flat-square" alt="Platform">
  <img src="https://img.shields.io/badge/Protocols-HTTP%2F1.1%20%7C%20HTTP%2F2%20%7C%20HTTP%2F3-00E5CC?style=flat-square" alt="Protocols">
  <img src="https://img.shields.io/badge/Built%20With-Flutter%20%2B%20Kotlin%20%2B%20C++-0553B1?style=flat-square&logo=flutter&logoColor=white" alt="Built With">
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-Proprietary-red?style=flat-square" alt="License"></a>
</p>

<p align="center">
  <a href="#download">Download</a> · <a href="#features">Features</a> · <a href="#architecture">Architecture</a> · <a href="#comparison">Comparison</a> · <a href="https://github.com/savaskarofficial/covert/issues">Report Issue</a>
</p>

---

## Download

<table>
  <tr>
    <th>Platform</th>
    <th>Download</th>
    <th>Requirements</th>
  </tr>
  <tr>
    <td>🤖 <strong>Android</strong></td>
    <td><a href="https://github.com/savaskarofficial/covert/releases/latest">APK (universal)</a></td>
    <td>Android 7.0+ (API 24)</td>
  </tr>
  <tr>
    <td>🪟 <strong>Windows</strong></td>
    <td><a href="https://github.com/savaskarofficial/covert/releases/latest">Installer (.exe)</a></td>
    <td>Windows 10/11 (x64)</td>
  </tr>
  <tr>
    <td>🐧 <strong>Linux</strong></td>
    <td><a href="https://github.com/savaskarofficial/covert/releases/latest">.deb (amd64)</a></td>
    <td>Debian 11+ / Ubuntu 20.04+ (x64)</td>
  </tr>
  <tr>
    <td>🍎 <strong>macOS</strong></td>
    <td>Coming soon</td>
    <td>macOS 12+</td>
  </tr>
</table>

> **Google Play**: Coming soon

---

## Features

### 🔒 Traffic Capture & MITM Proxy

- **Full HTTPS interception** with automatic CA certificate generation and one-tap installation
- **HTTP/2 frame-level MITM** — HPACK header decoding, stream multiplexing, not just byte piping
- **HTTP/2 ↔ HTTP/1.1 translation** — transparent protocol bridging when client and server differ
- **WebSocket** capture with real-time frame display, cross-chunk reassembly, and standalone WS client
- **Protocol support:** HTTP/1.x, HTTP/2, HTTP/3 (QUIC), HTTPS (TLS 1.1–1.3), SOCKS4/4a/5
- **Compression:** gzip, deflate, brotli (pure Dart), zstd (native FFI) — auto-detect by magic bytes
- **VPN mode** on Android — captures all traffic without Wi-Fi proxy configuration
- **System proxy** auto-configuration on Windows, macOS, Linux
- **Per-app filtering** on Android — choose which apps route through the proxy
- **SSL bypass** list — skip TLS inspection for pinned/sensitive hosts

### 🚀 API Client

- **HTTP/1.1** via `dart:io HttpClient`
- **HTTP/2** via native ALPN (`package:http2`)
- **HTTP/3 (QUIC)** via Cronet on Android, H2 fallback on desktop
- **Tabbed interface** with multiple concurrent requests
- **Environment variables** with `{{variable}}` syntax — isolated per environment, global fallback
- **Collections** with folder organization, import from Postman
- **8 auth types:** Bearer, Basic, Digest (auto-retry), NTLM, API Key, OAuth 2.0 (browser flow), AWS SigV4
- **Body types:** JSON, XML, Form Data, URL Encoded, Binary upload, GraphQL
- **Pre-request & post-response scripting** (JavaScript DSL)
- **Cookie manager** with auto-save across requests

### 💻 Code Snippets — 25 Languages

Generate ready-to-run code from any captured or composed request:

| Language | Libraries |
|----------|-----------|
| **Shell** | cURL |
| **C** | libcurl |
| **C#** | HttpClient, RestSharp |
| **Dart** | Dio, http (IOClient) |
| **Go** | net/http |
| **Java** | OkHttp, HttpClient, Unirest |
| **JavaScript** | Axios, Fetch, jQuery, XHR |
| **Kotlin** | OkHttp |
| **Node.js** | Axios, Fetch, Native http/https, Request |
| **PHP** | cURL, Guzzle |
| **Python** | Requests, http.client |
| **Ruby** | Net::HTTP |
| **Swift** | URLSession |

**Snippet Converter:** Paste code in any of 13 source languages → extract request → convert to any of the 25 output languages.

### ⚙️ Rule Engine — 9 Categories

| Rule | Description |
|------|-------------|
| **Rewrite** | Modify URL, request/response headers, request/response body (regex) |
| **Gateway** | Block requests (custom status + body) or suspend |
| **Mirror** | Duplicate traffic to a secondary host with full response capture |
| **Map Local** | Serve local files as response (JSON, HTML, JS, XML) |
| **Map Remote** | Redirect requests to different URL (regex capture groups) |
| **Highlight** | Color-tag matching traffic for visual filtering |
| **Network Condition** | Throttle bandwidth, add latency, simulate packet loss (presets: Offline, 2G, 3G, 4G) |
| **Breakpoint** | Pause request and/or response for manual inspection and editing |
| **DNS Override** | Route traffic to custom IP without modifying the request |

Each rule supports: 11 match fields × 8 operators, AND/OR logic, priority ordering, drag-to-reorder, enable/disable toggle, JSON import/export.

### 🖥️ Mock Server

- Shelf-based HTTP server on configurable port
- Route matching with `:param` wildcards
- Response body editor, custom headers, status codes
- Artificial delay, priority ordering, CORS auto-headers
- Request hit count tracking and logging

### 🧰 Toolbox — 14 Tools

Base64 encoder/decoder, URL codec, MD5/SHA hash generator, JSON formatter, XML formatter, HEX viewer, Image viewer, JWT decoder, QR code generator, Regex tester, Timestamp converter, Response diff viewer, Random data generator, Color picker

### 🤝 Collaboration

- QR code pairing for mobile ↔ desktop traffic forwarding
- Real-time traffic sync between devices

### 📦 Additional Features

- **Breakpoint editor** — edit request/response headers, body, URL, method before forwarding
- **History** — all traffic persisted to SQLite, survives app restart
- **Favorites** — bookmark requests, accessible even after clearing live traffic
- **HAR import/export** — standard `.har` format with file association on Windows & Android
- **13 editor themes** with customizable accent colors
- **Syntax highlighting** for JSON, XML, HTML, CSS, JavaScript, YAML, Markdown
- **AI traffic analysis** powered by Claude API

---

## Architecture

```
┌──────────────────────────────────────────────────────────────┐
│                        Covert Engine                          │
├──────────────────────────────────────────────────────────────┤
│                                                               │
│  Client ──TLS──▶ MITM Proxy (Dart Isolate)                   │
│                       │                                       │
│               ALPN negotiation                                │
│               ┌───────┴───────┐                              │
│               │               │                              │
│            h2 ▼            h1.1 ▼                            │
│   H2 Frame-Level        Transparent                          │
│   MITM Handler          Byte Pipe                            │
│    ↕ HPACK decode       + Http1Parser                        │
│    ↕ Stream mux         + WS frame capture                   │
│   H2↔H1 Translation    + Rule pipeline                      │
│   Handler                                                     │
│               │               │                              │
│               ▼               ▼                              │
│  SecureSocket [h2/h1.1] ──TLS──▶ Upstream Server             │
│                                                               │
├──────────────────────────────────────────────────────────────┤
│  API Client:  H1 (dart:io)  │  H2 (package:http2)           │
│               H3 (Cronet/QUIC on Android, H2 fallback)       │
├──────────────────────────────────────────────────────────────┤
│  Rule Engine: Rewrite │ Gateway │ Breakpoint │ Script        │
│               Mirror  │ Map Local │ Map Remote │ Highlight   │
│               Throttle │ DNS Override                         │
├──────────────────────────────────────────────────────────────┤
│  Storage:     SQLite (traffic + history + rules + settings)  │
│               JSON (collections, environments, mock routes)   │
│               Backup/restore with versioned JSON archives     │
├──────────────────────────────────────────────────────────────┤
│  Native:      zstd (FFI — C library, bundled per-platform)   │
│               Cronet (Kotlin bridge, Android only)            │
│               VPN (Kotlin TcpProxyStack, Android only)        │
└──────────────────────────────────────────────────────────────┘
```

**Tech Stack:** Flutter 3.22+ / Dart 3.4+, Kotlin (Android VPN + Cronet bridge), BLoC architecture, SQLite (raw sqlite3), GoRouter, PointyCastle (TLS/cert), BoringSSL (native)

**Codebase:** 306 Dart files, 11 Kotlin files, 73,000+ lines of code

---

## Comparison

| Feature | Covert | Reqable | Charles | Fiddler | Postman |
|---------|--------|---------|---------|---------|---------|
| **HTTP/2 MITM** | ✅ Frame-level | ✅ Request-level | ❌ | ❌ | — |
| **HTTP/3 API Client** | ✅ Cronet | ✅ | ❌ | ❌ | ❌ |
| **Code Snippets** | 25 targets | 22 targets | ❌ | ❌ | ✅ |
| **Snippet Converter** | ✅ 13→25 langs | ❌ | ❌ | ❌ | ❌ |
| **Auth Types** | 8 (OAuth2, AWS, NTLM, Digest) | 3 | 1 | 1 | ✅ |
| **WebSocket Client** | ✅ | ✅ | Capture only | Capture only | ❌ |
| **Collections + Env** | ✅ | ✅ + Cloud | ❌ | ❌ | ✅ |
| **Breakpoints** | ✅ Unlimited | ✅ (3 free) | ✅ | ✅ | ❌ |
| **Mock Server** | ✅ | ❌ | ❌ | ❌ | ✅ |
| **DNS Override** | ✅ (HTTPS CONNECT) | Host redirect | ✅ | ❌ | ❌ |
| **Mirror** | ✅ + response capture | ❌ | ✅ | ❌ | ❌ |
| **Protobuf Viewer** | ✅ | ❌ | ❌ | ❌ | ❌ |
| **zstd Decompression** | ✅ Native FFI | ❌ | ❌ | ❌ | ❌ |
| **Network Throttling** | ✅ 4 presets + manual | ✅ 9 presets | ✅ | ❌ | ❌ |
| **VPN Mode (Android)** | ✅ | ✅ | ❌ | ❌ | ❌ |
| **Toolbox** | 14 tools + JWT | 14 tools + AES | ❌ | ❌ | ❌ |
| **Cross-platform** | 4 OS | 5 OS | 3 OS | 2 OS | 5 OS |
| **Price** | **Free / $6 mo / $55 yr** | Free (limited) / $50/yr | $50 | $12/mo | Freemium |

---

## Platform Support

| Platform | Proxy | API Client | Notes |
|----------|-------|------------|-------|
| **Windows** | ✅ | ✅ | System proxy auto-config, Inno Setup installer |
| **macOS** | ✅ | ✅ | Network extension for system proxy |
| **Linux** | ✅ | ✅ | gsettings-based proxy configuration |
| **Android** | ✅ | ✅ | VPN mode, per-app filtering, Cronet HTTP/3, PiP mode |

---

## Getting Started

1. **Download** the latest release for your platform from [Releases](https://github.com/savaskarofficial/covert/releases/latest)
2. **Install** — run the installer (Windows), install the .deb (Linux), or install the APK (Android)
3. **Generate CA Certificate** — go to Certificates tab → Generate → Install to System
4. **Start Proxy** — tap the Play button on the Traffic tab
5. **Capture traffic** — browse normally, all HTTPS traffic is intercepted and displayed

---

## Contact

| | |
|---|---|
| **Website** | [undercoveritfirm.com](https://undercoveritfirm.com) |
| **Email** | [support@undercoveritfirm.com](mailto:support@undercoveritfirm.com) |
| **Telegram** | [@undercoveritfirm](https://t.me/undercoveritfirm) |
| **Developer** | [@savaskarofficial](https://t.me/savaskarofficial) |
| **Issues** | [GitHub Issues](https://github.com/savaskarofficial/covert/issues) |

---

<p align="center">
  <strong>Covert</strong> — HTTP Debugger & API Client<br>
  <em>Undercover IT Firm · Sharodshahi Al-Amin</em><br>
  Built with precision in Dhaka 🇧🇩<br><br>
  © 2024–2026 Undercover IT Firm. All rights reserved.
</p>
