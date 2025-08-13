# Unity Server

A lightweight, zero-dependency Node.js web server specifically designed for serving Unity WebGL builds locally and across networks.

## Features

- 🚀 **Zero dependencies** - Uses only Node.js built-in modules
- 🔍 **Auto port detection** - Finds the first available port automatically
- 🌐 **Network access** - Provides local IP address for testing on other devices
- 🎮 **Unity WebGL optimized** - Includes proper MIME types and CORS headers
- 🗜️ **Compression support** - Handles both Brotli (.br) and Gzip (.gz) files
- 🔒 **Security** - Prevents directory traversal attacks
- 🎯 **Simple to use** - Just run in your WebGL build folder

## Installation

### Global Installation (Recommended)

```bash
npm install -g @sov3rain/unity-server
```

Then use anywhere:
```bash
unity-serve
```

### Local Installation

```bash
npm install @sov3rain/unity-server
```

Or download the `server.js` file directly and run with Node.js.

## Usage

### Method 1: Global Command (if installed globally)

Navigate to your Unity WebGL build folder and run:
```bash
unity-serve
```

### Method 2: NPX (without installation)

```bash
cd path/to/your/unity-webgl-build
npx @sov3rain/unity-server
```

### Method 3: Direct Node.js

```bash
cd path/to/your/unity-webgl-build
node server.js
```

## What You'll See

When you start the server, you'll see output like this:

```
🎮 Unity WebGL Server Started!
📁 Serving files from: /path/to/your/build
🌐 Local URL: http://localhost:3000
📱 Network URL: http://192.168.1.100:3000
⏹️  Press Ctrl+C to stop the server
```

## Testing on Other Devices

Use the **Network URL** to test your Unity WebGL build on:
- Mobile phones
- Tablets  
- Other computers on the same network
- VR headsets with browsers

Just open the Network URL in any web browser on devices connected to the same WiFi/network.

## Unity WebGL Build Requirements

Your Unity WebGL build folder should contain:
- `index.html` (required - the server checks for this)
- Build files (`.js`, `.wasm`, `.data` files)
- Any compressed files (`.gz`, `.br`)

Typical Unity WebGL build structure:
```
your-build-folder/
├── index.html
├── Build/
│   ├── your-game.loader.js
│   ├── your-game.framework.js(.br/.gz)
│   ├── your-game.data(.br/.gz)
│   ├── your-game.wasm(.br/.gz)
│   └── your-game.symbols.json(.br/.gz)
├── TemplateData/
│   ├── favicon.ico
│   ├── fullscreen-button.png
│   ├── progress-bar-empty-dark.png
│   ├── progress-bar-full-dark.png
│   ├── unity-logo-dark.png
│   └── webgl-logo.png
└── StreamingAssets/ (if any)
```

## Troubleshooting

### "No index.html found" Error
Make sure you're running the server in the correct folder:
```bash
cd path/to/your/unity-webgl-build
# Should contain index.html
unity-serve
```

### Can't Access from Other Devices
1. **Check firewall** - Ensure your firewall allows the port
2. **Same network** - Devices must be on the same WiFi/network
3. **Use Network URL** - Use the IP address shown, not localhost

## License

MIT License - Feel free to use in your projects!