# SillyTavern Python Bridge

A SillyTavern extension that enables bidirectional communication between Python programs and SillyTavern chat.

## Installation

1. Copy this entire folder to your SillyTavern's `extensions` directory
2. Restart SillyTavern
3. Enable the extension using the `/python-bridge on` command in SillyTavern chat

## Python Setup

1. Install Python requirements:
   ```bash
   pip install -r requirements.txt
   ```

2. Run the chat client:
   ```bash
   python st_chat.py
   ```

## Usage

1. Make sure SillyTavern is running and the extension is enabled
2. Run the Python chat client
3. Type messages in the Python console to send them to SillyTavern
4. Bot responses will automatically appear in the Python console
5. Type 'exit' to quit the chat

## Configuration

- The default WebSocket port is 5001
- You can change this in SillyTavern's extension settings
- If you change the port, update the `websocket_url` in the Python script

## Troubleshooting

1. If the connection fails:
   - Make sure SillyTavern is running
   - Verify the extension is enabled
   - Check if the port is available
   - Look for any error messages in the browser console

2. If messages aren't sending:
   - Check your internet connection
   - Verify the WebSocket connection is established
   - Look for error messages in the Python console

## Contributing

Feel free to submit issues and pull requests! #   T a v e r n - p y t h o n - B r i d g e  
 