<p align="center">
  <img src="assets/icon/covert_logo_1024.png" alt="Covert" width="160" />
</p>

# Covert

Covert is an HTTP debugger, HTTPS interception proxy and API client from [Undercover IT Firm](https://undercoveritfirm.com). Use it to inspect requests, troubleshoot responses, test APIs and change traffic with rules.

[![Download latest release](https://img.shields.io/badge/Download-Latest%20release-00897B?style=for-the-badge)](https://github.com/savaskarofficial/covert/releases/latest)

Android APK, Linux AppImage and Debian packages are available through the release page. Check its notes for system requirements and installation steps. Windows installers remain available in earlier releases. A macOS installer is not currently published.

## Traffic capture and inspection
Inspect requests, response headers and bodies, connection details and timing. Use the list or host view, quick filters and advanced search to find a session. Bookmark, comment on or highlight useful requests, then replay them, add them to a collection, compare them or export them as HAR, raw HTTP, cURL or code snippets.

Covert supports HTTP/1.1 and HTTP/2 interception, including translation between those protocols. Android capture uses a local VPN service with per-app selection; desktop builds use the proxy path. DNS queries handled by the Android VPN resolver can also appear in Traffic. WebSocket sessions include a frame viewer, and the API client has a separate WebSocket client.

HTTPS inspection requires the client to trust the Covert CA. Pinned applications may reject that certificate; bypassed traffic remains encrypted. The proxy does not decrypt HTTP/3 traffic. Streaming response captures retain up to 2 MiB as a preview and their full received byte count, so saving a partial preview does not export a complete larger video or file.

## API client and collections

Create requests in separate tabs with custom methods, parameters, headers, cookies, authentication and connection settings. Send JSON, XML, form data, URL-encoded content, binary files or GraphQL requests. Inspect response bodies, cookies, timing and raw messages, including live Server-Sent Events.

Supported authentication includes Basic, Bearer, API keys, Digest, NTLM, OAuth and AWS request signing. Environment and collection variables let saved requests switch between servers and credentials. Requests can use custom proxies, redirects and timeouts. The Android API client supports HTTP/3 through Cronet where available; other transports can fall back to HTTP/2 or HTTP/1.1.

Organize saved requests in nested folders. Import Postman, Insomnia, Hoppscotch, OpenAPI/Swagger, HAR, raw HTTP and native Covert collections. Export collections, generate request code for supported libraries, convert existing snippets and export collection test runners for CI/CD.

## Scripts and request chains

Use JavaScript before a request, after a response or in a standalone run. Reusable scripts can change request or response data, extract values, assert results and update environment variables. The visual script editor builds nested conditions, loops, assertions and data transformations without writing every line by hand. Scripts run in a bounded QuickJS environment with execution and memory limits; browser and Node.js host APIs are not provided.

Request Chain runs saved or captured requests in order. Pass values between steps using response fields, headers, cookies and environment variables. Add delays, assertions, pre/post-step scripts and stop-on-error behavior, then save the chain for another run.

## GraphQL, gRPC and load testing

The GraphQL client sends queries and mutations with variables and custom headers, browses available schemas through introspection and keeps request history.

The gRPC client loads .proto files, encodes and decodes protobuf, lists services through reflection and accepts request metadata. Native HTTP/2 supports unary and server-streaming calls plus queued client and bidirectional messages. gRPC-Web supports unary and buffered finite server streams; load .proto files for complete method and message schemas.

Load Tester runs count, duration and target-rate tests with configurable concurrency, warm-up, ramp-up, spike and step-up patterns. Use response/error assertions, saved profiles and JSON reports to compare measured throughput, latency and failures. Actual rates depend on the device, network and server.

## Rules and API comparison

Match traffic by request and response fields, combine conditions and set priorities. Rewrite URLs, headers or bodies; block, suspend or mirror requests; map responses to local files or remote URLs; override DNS destinations; add latency or bandwidth limits; set breakpoints; and highlight matching sessions.

API Diff compares requests from captured Traffic, the API client and Collections. It can compare URLs, authentication, headers, bodies and connection options. Response comparisons are available when the selected source includes a response snapshot.

## Covert Server

Build mock API projects with configurable routes, response bodies, headers, status codes, CORS settings and delays. Dynamic CRUD routes provide editable data with filtering, sorting and pagination. Mock authentication, WebSocket routes, Server-Sent Events and fault simulation help test client behavior.

Projects keep their routes, data, sessions and uploaded files across restarts. Inspect requests in the server log or export a Node.js/Express project for the supported route and export modes. Mock authentication is intended for testing, and exported deployments require their own reviewed configuration.

## Toolbox and certificate tools

The Toolbox includes Base64 and URL codecs, hashes, JSON and XML formatting, HEX and image viewers, text comparison, regular expressions, timestamps, random data, QR codes and color conversion. JWT tools can inspect and edit claims, generate tokens and sign or verify supported algorithms. Smart Auth Inspector identifies common token and authentication formats.

Certificate tools generate and export the Covert CA, show certificate details and explain platform trust setup. The SSL pinning helper provides configuration and common hook templates for authorized app testing; support depends on the client implementation.

## Collaboration, saved work and settings

Share live Traffic between paired devices on the local network, using QR pairing or a session key. The optional report server serves a token-protected traffic viewer. LAN access controls do not make these connections TLS-encrypted, so use a trusted network.

History, favorites and saved projects preserve work between sessions. Local backup and restore covers supported app-managed data. Where the account plan enables Cloud Sync, supported collections, environments, rules, scripts, chains, mock projects, favorites and settings can sync between devices. Cloud Sync does not replace a complete local traffic backup.

Settings control the proxy port, upstream proxy, automatic capture, HTTP/2 interception, Turbo mode, cache-related response headers, per-app filters, host access rules, capture limits and history retention. Appearance, supported app locks, keyboard shortcuts and debug logs are also available. Account controls manage sign-in, device sessions and plan access. Some features depend on the platform or account plan.

## Get started

1. Install the package for your platform. On Android, open the APK and allow installation from your browser or file manager if prompted. On Linux, make the AppImage executable or install the Debian package with your package manager.
2. Start capture from the Traffic tab. Use Android VPN mode or configure the client to connect to the proxy address and port shown by Covert.
3. For HTTPS inspection, generate the Covert CA in Certificates and follow the trust setup instructions on the client being tested.
4. Open the app or website, then return to Traffic to inspect its requests and responses.

After changing interception or Turbo settings, reconnect the client to apply connection-level settings. Detailed controls, examples and platform notes are available in Covert's built-in Documentation.

## Report a problem

Open a [GitHub issue](https://github.com/savaskarofficial/covert/issues) with the Covert version, operating system, steps to reproduce and the error message. For connection problems, include whether VPN capture, manual proxy or HTTP/2 interception was enabled.

HAR files can contain cookies, authorization headers and private request data. Remove those values before attaching a capture to a public issue.

## License and contact

Covert is proprietary software. See [LICENSE](LICENSE) for its terms. This repository provides release downloads and product information.

- Website: [undercoveritfirm.com](https://undercoveritfirm.com)
- Support: [support@undercoveritfirm.com](mailto:support@undercoveritfirm.com)
- Telegram: [Undercover IT Firm](https://t.me/undercoveritfirm)
- Developer: [Sharodshahi Al-Amin](https://t.me/savaskarofficial)

Copyright (c) 2024-2026 Undercover IT Firm. All rights reserved.
