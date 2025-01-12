# Tavern-python-Bridge

A SillyTavern extension that enables bidirectional communication between Python programs and SillyTavern chat. This extension allows you to send messages to and receive responses from SillyTavern through Python scripts, making it perfect for automation, bot integration, or custom applications.

## Features

- 🔌 Bidirectional WebSocket communication
- 🐍 Python API for easy integration
- 🎮 Visual control panel in SillyTavern
- 🔄 Automatic reconnection
- 📊 Real-time connection status
- ⚡ Low latency message passing
- 📦 Automatic package installation

## Installation

### Method 1: Install from Git (Recommended)
1. In SillyTavern, go to **Extensions** > **Install Extensions**
2. Click **Install from Git**
3. Enter: `https://github.com/Dopamage/Tavern-python-Bridge`
4. Click Install
5. Restart SillyTavern

### Method 2: Manual Installation
1. Download this repository
2. Copy the entire folder to:
   ```
   SillyTavern/public/scripts/extensions/third-party/Tavern-python-Bridge/
   ```
3. Restart SillyTavern

## Python Setup

The script will automatically check for and install required packages on first run. Just run:
```bash
python st_chat.py
```

If you prefer to install packages manually:
```bash
pip install -r requirements.txt
```

Required packages:
- websockets
- asyncio
- typing

## Usage

### In SillyTavern
1. Go to Extensions (puzzle piece icon)
2. Find "Python Bridge" in the extensions list
3. Enable the extension using either:
   - Toggle the checkbox in the UI
   - Use command: `/python-bridge on`
4. Configure port if needed (default: 5001)

### Using the Python API

Basic usage:
```python
from st_chat import SillyTavernBridge, ConsoleChat

# Simple console chat
async def main():
    bridge = SillyTavernBridge(port=5001)
    chat = ConsoleChat(bridge)
    await chat.start_chat()

asyncio.run(main())
```

Custom integration:
```python
from st_chat import SillyTavernBridge

class MyCustomHandler:
    def __init__(self):
        self.bridge = SillyTavernBridge(port=5001)
        
        # Set up callbacks
        self.bridge.add_message_callback(self.on_message)
        self.bridge.add_response_callback(self.on_response)
        self.bridge.add_error_callback(self.on_error)
        
    def on_message(self, author: str, message: str):
        print(f"Message sent: {author} -> {message}")
        
    def on_response(self, response: str):
        print(f"Bot response: {response}")
        
    def on_error(self, error: str):
        print(f"Error: {error}")
        
    async def start(self):
        await self.bridge.start_server()
        
    async def send_message(self, message: str):
        await self.bridge.send_message(message)
```

## Configuration

### Extension Settings
- **Port**: WebSocket server port (default: 5001)
- **Auto-reconnect**: Automatically tries to reconnect if connection is lost
- **Status Indicator**: Shows current connection status

### Python Configuration
- **Port**: Must match the port set in SillyTavern
- **Host**: Default is "0.0.0.0" (allows external connections)
- **Callbacks**: Can be configured for custom message handling

## Troubleshooting

### Common Issues

1. Connection Refused
   - Ensure Python server is running
   - Check if port is available
   - Verify firewall settings

2. Messages Not Sending
   - Check connection status in UI
   - Verify WebSocket connection
   - Look for errors in browser console (F12)

3. Extension Not Found
   - Verify installation path
   - Clear browser cache
   - Restart SillyTavern

### Debug Tips
- Enable browser console (F12) to see connection logs
- Check Python console for server messages
- Verify port settings match in both SillyTavern and Python

## Development

Want to contribute? Great! Here's how:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

MIT License - feel free to use in your own projects!

## Support

- GitHub Issues: [Report a bug](https://github.com/Dopamage/Tavern-python-Bridge/issues)
- Discord: [Join our community](your_discord_link)

## Changelog

### v1.0.0
- Initial release
- Basic WebSocket communication
- UI Integration
- Python API
- Automatic reconnection
- Status monitoring
 
 