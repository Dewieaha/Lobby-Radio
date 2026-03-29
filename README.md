Lobby Chat

Serverless peer-to-peer voice chat and text chat using WebRTC (PeerJS). No persistent backend required.

Overview

Lobby Chat is a browser-based voice communication system that forms a fully peer-to-peer mesh network between participants. The first user to join a room claims a predictable anchor ID. Subsequent users connect to that anchor and receive a list of peers, allowing the network to self-organize into a full mesh.

After initial signaling, all audio traffic is transmitted directly between clients.

Features

- Peer-to-peer voice communication (WebRTC)
- No backend required after connection establishment
- Dynamic participant discovery and mesh formation
- Speaking detection and visual indicators
- Mute, deafen, and push-to-talk controls
- Host election and manual host reassignment
- Invite link generation

Demo

https://lobbychat.netlify.app/

Usage

1. Open the application in a browser
2. Enter a callsign (username)
3. Enter a room ID
4. Join the lobby
5. Share the invite link with others

Push-to-talk uses the V key when enabled.

How It Works

- A normalized room ID is used to derive a deterministic anchor peer ID
- The first peer to claim the anchor becomes the initial host
- New peers attempt to connect to the anchor and known slot IDs
- The anchor shares a peer list to bootstrap mesh connections
- Each peer establishes direct data and media connections with others

This avoids centralized session management.

Limitations

- Mesh topology scales poorly for large rooms (O(n^2) connections)
- Some NAT configurations may require TURN relays
- Requires browser microphone permissions
- No persistence or authentication layer

Tech Stack

- WebRTC
- PeerJS
- Vanilla JavaScript
- Single-file application (index.html)

Running Locally

Open index.html directly in a browser, or serve it via a simple HTTP server.

Example:

python -m http.server

License

No license. All rights reserved.

**Full Changelog**: https://github.com/Dewieaha/Lobby-Radio/commits/Webrtc
