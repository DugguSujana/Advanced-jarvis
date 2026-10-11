# Advanced-jarvis
Advanced Jarvis - Personal Voice Assistant for Windows
A powerful, context-aware voice assistant for Windows that listens, understands, and executes voice commands to help you work faster and hands-free.
🚀 Key Features
Voice Control & System Integration
Voice launch & control: Open apps, switch windows, manage browser tabs
System control: Volume, brightness, Bluetooth, Wi-Fi, battery saver, screenshots
File-aware actions: Search files, analyze uploaded content, safe file operations
Smart responses: Context-aware replies with follow-up understanding
Advanced Capabilities
Gesture Controls: Virtual mouse, volume/brightness control, virtual keyboard
Web Integration: Google/Wikipedia/YouTube search with smart summaries
Productivity: Email composition, note-taking, reminders, weather updates
Automation: Generate code snippets, run searches, create files
Multi-language: Works with multiple languages and translation
Privacy & Security
Privacy-minded: You control what's processed and saved
Permission prompts: Confirmations for destructive actions
Local storage: Optional conversation history with configurable retention
Secure credentials: Environment-based API key management
🛠️ Installation
Prerequisites
Windows 10/11
Python 3.8+
Microphone and speakers/headphones
Webcam (optional, for gesture controls)
Setup Steps
Clone or download this repository
Install dependencies:
```bash
   pip install -r requirements.txt
   ```
Configure API keys:
Copy `.env.example` to `.env`
Add your API keys (see Configuration section below)
Run the application:
```bash
   python main.py
   ```
⚙️ Configuration
Required API Keys
Google Cloud (for Speech-to-Text and Generative AI)
Go to Google Cloud Console
Create a new project or select existing
Enable Speech-to-Text API and Generative AI API
Create service account and download JSON key file
Get Generative AI API key from AI Studio
OpenWeatherMap (for weather updates)
Sign up at OpenWeatherMap
Get your free API key
Email (optional)
Gmail: Enable 2FA and create app password
Outlook: Use account credentials or app password
Environment Variables
Edit `.env` file with your configuration:
```env
GOOGLE_CLOUD_PROJECT_ID=your-project-id
GOOGLE_APPLICATION_CREDENTIALS=path/to/service-account.json
GOOGLE_GENERATIVE_AI_API_KEY=your-gemini-api-key
OPENWEATHERMAP_API_KEY=your-weather-api-key
# ... see .env.example for all options
```
🎯 Usage
Voice Commands Examples
System Control
"Increase volume to 80%"
"Turn on Bluetooth"
"Take a screenshot"
"Set brightness to 50%"
App Control
"Open Chrome"
"Switch to Visual Studio Code"
"Close current tab"
"Open calculator"
Web & Search
"Search Google for Python tutorials"
"What's the weather in New York?"
"Open YouTube and search for jazz music"
"Tell me about artificial intelligence from Wikipedia"
File Operations
"Search for files containing 'budget'"
"Create a new folder called 'Projects'"
"Show me recent documents"
Productivity
"Set an alarm for 7:30 AM"
"Wake me up in 15 minutes"
"Show my alarms"
"Stop alarm"
"Set a reminder for 3 PM to call the dentist"
"Take a note: Meeting with client tomorrow"
"Tell me a joke"
Communication
"Call [Contact Name]" (WhatsApp Voice Call)
"Video call to [Contact Name]" (WhatsApp Video Call)
"Send a message to [Contact Name]: I'll be there soon" (WhatsApp Message)
"Chat with [Contact Name]" (Open WhatsApp Chat)
GUI Controls
Push-to-talk: Hold spacebar or click microphone button
Theme toggle: Switch between light and dark modes
Settings: Configure voice, TTS, and feature toggles
Logs: View command history and system status
🏗️ Architecture
```
advanced-jarvis/
├── core/                 # Core application logic
│   ├── jarvis_app.py    # Main application class
│   ├── config.py        # Configuration management
│   ├── logger.py        # Logging setup
│   └── context.py       # Context and memory management
├── services/            # Core services
│   ├── speech/          # Speech recognition
│   ├── tts/             # Text-to-speech
│   ├── nlu/             # Natural language understanding
│   └── dispatcher/      # Command routing and execution
├── plugins/             # Feature plugins
│   ├── system/          # System controls
│   ├── apps/            # Application control
│   ├── search/          # Web search and information
│   ├── files/           # File operations
│   ├── utilities/       # Screenshots, notes, weather, etc.
│   ├── email/           # Email functionality
│   └── gestures/        # Gesture recognition
├── gui/                 # User interface
└── data/                # Local storage and logs
```
🔧 Development
Running in Development Mode
```bash
# Install development dependencies
pip install -r requirements.txt

# Run with debug logging
LOG_LEVEL=DEBUG python main.py

# Run tests
pytest tests/
```
Building Executable
```bash
# Create standalone executable
pyinstaller --onefile --windowed main.py
```
🤝 Contributing
Fork the repository
Create a feature branch
Make your changes
Add tests if applicable
Submit a pull request
📝 License
This project is licensed under the MIT License - see the LICENSE file for details.
🆘 Troubleshooting
Common Issues
Microphone not working:
Check Windows microphone permissions
Verify microphone is set as default recording device
Test with `python -m speech_recognition`
Google Cloud errors:
Verify service account JSON file path
Check API quotas and billing
Ensure required APIs are enabled
System control not working:
Run as administrator for some system operations
Check Windows UAC settings
Verify required Windows features are enabled
Support
Check the logs in `data/logs/` for detailed error information
Review the configuration in `.env`
Test individual components using the GUI's debug mode
🎉 Acknowledgments
Built with modern Python libraries:
CustomTkinter for beautiful GUI
Google Cloud Speech & Generative AI
MediaPipe for gesture recognition
pycaw for Windows audio control
And many other excellent open-source libraries
