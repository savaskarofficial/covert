<p align="center">
  <img src="assets/icon/covert_logo_1024.png" alt="Covert" width="160" />
</p>

# Covert

Covert is an HTTP debugger, HTTPS interception proxy and API client from [Undercover IT Firm](https://undercoveritfirm.com). Use it to inspect requests, troubleshoot responses, test APIs and change traffic with rules.

## Download

**Latest Android release: 1.14.8, build 223.** Requires Android 7.0 or newer on an ARM64 or ARMv7 device.

[Download the Android APK](https://github.com/savaskarofficial/covert/releases/download/v1.14.8/Covert-1.14.8-android-universal.apk) | [Release notes](https://github.com/savaskarofficial/covert/releases/tag/v1.14.8)

This release contains the Android APK. The previous desktop downloads remain available below.

| Platform | Available version | Download |
| --- | --- | --- |
| Android | 1.14.8 | [APK](https://github.com/savaskarofficial/covert/releases/download/v1.14.8/Covert-1.14.8-android-universal.apk) |
| Windows x64 | 1.14.2 | [Installer](https://github.com/savaskarofficial/covert/releases/download/v1.14.2/Covert-1.14.2-windows-x64-setup.exe) |
| Debian and Ubuntu amd64 | 1.14.2 | [Debian package](https://github.com/savaskarofficial/covert/releases/download/v1.14.2/covert_1.14.2_amd64.deb) |
| Linux x86_64 | 1.14.2 | [AppImage](https://github.com/savaskarofficial/covert/releases/download/v1.14.2/Covert-1.14.2-linux-x86_64.AppImage) |

There is no macOS installer in the current releases.

## What's new in 1.14.8

- Certificate generation no longer pauses unrelated network transfers.
- HTTP/2 handles receive windows, upstream stream limits and slow receivers more reliably.
- Turbo settings reach the running proxy and apply to new connections.
- Unrelated response rewrite rules no longer hold video responses until the download finishes. Range responses continue to stream.
- Traffic records keep the received body size and identify partial capture previews when displaying or saving them.
- Earlier traffic search, API client, rules and WebSocket fixes are included.

## Traffic capture

Capture HTTP and HTTPS traffic, inspect headers and bodies, filter sessions and export requests for further testing.

- HTTP/1.1 and HTTP/2 interception, including translation between the two protocols.
- Android VPN capture with per-app selection, plus manual proxy connections from other devices.
- WebSocket frame inspection and a separate WebSocket client.
- Response viewers for text, JSON, XML, images, binary data and other supported body types.
- Session history, favorites, HAR import and export, and request replay.
- Host bypass rules for connections that should pass through without TLS inspection.

HTTPS inspection requires the client to trust Covert's CA certificate. Some apps reject user-installed certificates or use certificate pinning. Bypassed connections remain encrypted and do not provide decrypted request bodies.

Streaming response captures retain up to 2 MiB as a preview. Covert records the full received byte count, but saving a partial preview does not save the complete larger response or video.

## API client and collections

Compose requests, organize them in collections and reuse values across environments.

- Request tabs, headers, query parameters, cookies and configurable timeouts.
- JSON, XML, form data, URL-encoded, binary and GraphQL request bodies.
- Basic, Bearer, API key, Digest, NTLM, OAuth 2.0 and AWS Signature authentication.
- Environment variables using `{{variable}}` syntax, with collection import and export.
- JavaScript hooks before requests and after responses.
- Code snippet generation and conversion for supported languages and libraries.
- Request chains, GraphQL tools, response comparison and load testing.

The Android API client supports HTTP/3 through Cronet where available. The proxy does not decrypt HTTP/3 traffic; QUIC passthrough stays encrypted.

## Rules and mock server

Use matching conditions and priorities to control selected requests and responses.

| Tool | Purpose |
| --- | --- |
| Rewrite | Change URLs, headers or bodies. |
| Gateway | Block or suspend matching requests. |
| Map Local | Serve a local file as a response. |
| Map Remote | Route a request to another URL. |
| Mirror | Send a copy of traffic to a second destination. |
| Breakpoint | Pause a request or response for inspection and editing. |
| DNS override | Route a host to a chosen IP address. |
| Network conditions | Add latency or limit bandwidth for testing. |
| Highlight | Mark matching sessions in the traffic list. |

The mock server provides configurable routes, status codes, headers, response bodies, delays and request logs. Export options are available for supported server formats.

## Other tools

Covert includes encoding and decoding tools, hash generation, JSON and XML formatting, JWT inspection, regular expression testing, timestamps, QR codes and response comparison. Collaboration tools can share traffic between paired devices. Backups preserve supported settings and saved data.

Some features require an account or paid plan. Current pricing and plan details are shown in the app.

## Get started on Android

1. Download the APK from the release page and open it to install. Android may ask you to allow installation from your browser or file manager.
2. Open the Traffic tab and start capture. Accept Android's VPN permission when using VPN mode.
3. For HTTPS inspection, open Certificates and follow the certificate installation instructions. The device or app being tested must trust that certificate.
4. Open the app or website you want to inspect, then return to the traffic list to view its requests.

When connecting another device through the manual proxy, use the address and port shown by Covert. Install and trust the CA on that client if you need HTTPS inspection.

The APK uses the same application ID and signing certificate as the GitHub 1.14.2 release, with a higher build number. Install it over that version to update. Google Play installations may use a different signing key; back up saved data before switching installation channels.

After updating, restart capture and reconnect the client so new connections use the updated engine. Existing HTTP/2 connections keep their negotiated settings until they reconnect.

## Report a problem

Open a [GitHub issue](https://github.com/savaskarofficial/covert/issues) with the Covert version, device and Android version, steps to reproduce, and the error message. For connection problems, include whether VPN capture, manual proxy or HTTP/2 interception was enabled.

HAR files can contain cookies, authorization headers and private request data. Remove those values before attaching a capture to a public issue.

## License and contact

Covert is proprietary software. See [LICENSE](LICENSE) for its terms. This repository provides release downloads and product information.

- Website: [undercoveritfirm.com](https://undercoveritfirm.com)
- Support: [support@undercoveritfirm.com](mailto:support@undercoveritfirm.com)
- Telegram: [Undercover IT Firm](https://t.me/undercoveritfirm)
- Developer: [Sharodshahi Al-Amin](https://t.me/savaskarofficial)

Copyright (c) 2024-2026 Undercover IT Firm. All rights reserved.
