<p align="center">
  <img src="logo.png" alt="GameBoy Emulator ChatGPT" width="200"/>
</p>

<h1 align="center">GameBoy Emulator for ChatGPT</h1>

<p align="center">
  <strong>Play classic GameBoy games directly in your ChatGPT conversations</strong>
</p>

<p align="center">
  <a href="#features">Features</a> •
  <a href="#installation">Installation</a> •
  <a href="#usage">Usage</a> •
  <a href="#controls">Controls</a> •
  <a href="#tech-stack">Tech Stack</a>
</p>

---

A GameBoy emulator integration for ChatGPT, built as a **Model Context Protocol (MCP)** server. Upload and play GameBoy ROM files directly within ChatGPT conversations.

> Built with [Gameboy.js](https://github.com/juchi/gameboy.js/) and [CSS Gameboy](https://github.com/attackemartin/css-gameboy).

---

## Features

| Feature | Description |
|---------|-------------|
| **Browser-based Emulator** | Full GameBoy emulation embedded directly in ChatGPT |
| **ROM Support** | Upload `.gb` and `.gbc` ROM files |
| **Keyboard Controls** | Play using intuitive keyboard mappings |
| **Session Management** | State persists across your conversation |

---

## Installation

```bash
npm install
```

---

## Usage

### Development

```bash
npm run dev
```

> Starts the server with hot reload using nodemon.

### Production

```bash
npm run build
npm start
```

### Configuration

Set the `PORT` environment variable to customize the server port (defaults to 3000):

```bash
PORT=8080 npm start
```

---

## Controls

<table align="center">
  <tr>
    <th>Key</th>
    <th>Action</th>
  </tr>
  <tr>
    <td align="center"><kbd>↑</kbd> <kbd>↓</kbd> <kbd>←</kbd> <kbd>→</kbd></td>
    <td>D-Pad</td>
  </tr>
  <tr>
    <td align="center"><kbd>G</kbd></td>
    <td>A Button</td>
  </tr>
  <tr>
    <td align="center"><kbd>B</kbd></td>
    <td>B Button</td>
  </tr>
  <tr>
    <td align="center"><kbd>H</kbd></td>
    <td>START</td>
  </tr>
  <tr>
    <td align="center"><kbd>N</kbd></td>
    <td>SELECT</td>
  </tr>
</table>

---

## Tech Stack

<table>
  <tr>
    <td><strong>Backend</strong></td>
    <td>Node.js • TypeScript • Express • MCP SDK • Zod</td>
  </tr>
  <tr>
    <td><strong>Frontend</strong></td>
    <td>TypeScript • Vite • GameBoy.js • HTML5 Canvas</td>
  </tr>
</table>

---

## Project Structure

```
gameboy/
├── src/
│   ├── server.ts                    # Main MCP HTTP server
│   ├── extensions/
│   │   └── gameboy.extension.ts     # Tool registration
│   └── web/gameboy-player/
│       ├── gameboy-player.html      # UI template
│       ├── gameboy-player.ts        # Frontend logic
│       └── *.css                    # Styling
├── scripts/
│   └── build-web.ts                 # Vite build script
└── dist/                            # Compiled output
```

---

## API Endpoints

| Method | Path | Description |
|--------|------|-------------|
| `POST` | `/mcp` | MCP protocol handler |
| `GET` | `/mcp` | SSE stream for bidirectional communication |
| `DELETE` | `/mcp` | Session cleanup |

---

<p align="center">
  <sub>Made with ❤️ for retro gaming enthusiasts</sub>
</p>

## License

MIT
