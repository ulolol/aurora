# Aurora Chatbot 🌌

![Logo](aurora-logo_github.gif)

Aurora is a modern web-based chatbot that combines the power of Google's Gemini AI with real-time web search capabilities via Tavily. It features a sleek dark-themed interface with support for file attachments and conversation history management.

## Features

- **AI-Powered Conversations**: Uses Google's Gemini 2.5 Flash Lite model for intelligent responses
- **Dual Search Modes**:
  - **Web Search**: General web searches for current information
  - **Academic Search**: Filtered searches across 16+ academic sources (ArXiv, Scholar, PubMed, IEEE, etc.)
- **Search Mode Toggle**: Easy checkbox to enable/disable academic search with real-time label updates
- **File Attachments**: Upload and process various file types with your messages
- **Conversation Memory**: Maintains full conversation history for context-aware responses
- **Modern UI**: Beautiful dark theme with purple and cyan accent colors
- **Real-time Processing**: Live status updates during searches and file processing
- **Responsive Design**: Works on different screen sizes

## Setup Requirements

### API Keys

Aurora requires two API keys to function:

1. **Gemini API Key** - Get from [Google AI Studio](https://aistudio.google.com/apikey)
2. **Tavily API Key** - Get from [Tavily AI Search](https://tavily.com/)

### Configuration

Create a JSON file with your API keys in the following format:

```json
{
  "gemini": "your-gemini-api-key",
  "tavily": "your-tavily-api-key"
}
```

## Usage

1. Open `aurora.html` in a modern web browser
2. Click "Choose API Keys File" and select your JSON configuration file
3. Wait for the confirmation message
4. Start chatting with Aurora!

### Features

- **Text Messages**: Type messages naturally into the input field
- **File Attachments**: Click the paperclip icon to attach files
- **Web Search**: Aurora will automatically search the web when needed
- **Academic Search Mode**:
  - Toggle the 🎓 Academic Search checkbox before asking research questions
  - Aurora will prioritize academic sources like ArXiv, Google Scholar, PubMed, IEEE, ACM, and more
  - Mode indicator shows "Web Search" or "📚 Academic Search"
- **Keyboard Shortcuts**: Press Enter to send, Shift+Enter for new line
- **Message Status**: Track search queries, academic searches, and file processing in real-time

### Academic Search Sources

When Academic Search mode is enabled, Aurora searches across these 16+ authoritative academic sources:

| Source | Focus |
|--------|-------|
| ArXiv | Preprints in physics, CS, math, etc. |
| Google Scholar | Multi-disciplinary research |
| ResearchGate | Researcher network & papers |
| Semantic Scholar | AI-indexed academic papers |
| PubMed | Biomedical & life sciences |
| DOI.org | Digital object identifiers |
| IEEE | Engineering & technology |
| ACM | Computer science & IT |
| JSTOR | Humanities & social sciences |
| ScienceDirect | Multidisciplinary journals |
| Nature | Multidisciplinary research |
| Springer | Academic publishing |
| Wiley | Scientific publications |
| PLOS | Open-access journals |
| bioRxiv | Biology preprints |
| medRxiv | Medical preprints |

## Technical Stack

- **Frontend**: HTML5, CSS3, JavaScript (ES6+)
- **AI Model**: Google Gemini 2.5 Flash Lite
- **Search Engine**: Tavily AI Search API with domain filtering
- **Markdown Rendering**: Marked.js
- **Icons**: Font Awesome 6.5.2

## How Academic Search Works

Aurora uses Tavily's `include_domains` parameter to filter searches to academic sources when Academic Search mode is enabled:

1. **Mode Toggle**: User enables 🎓 Academic Search checkbox
2. **Tool Selection**: Gemini prioritizes the `academic_search` tool over `tavily_search`
3. **Domain Filtering**: Tavily API receives a whitelist of 16+ academic domains
4. **Advanced Search**: Academic searches use "advanced" depth for better relevance
5. **Result Processing**: Gemini synthesizes academic results with proper context

**Key Differences**:
- **Web Search**: Basic depth, unrestricted domains, up to 5 results
- **Academic Search**: Advanced depth, academic domains only, up to 5 results

## File Structure

```
aurora.html
├── HTML Structure
│   ├── Chat Header
│   ├── API Key Setup Panel
│   └── Chat Interface
├── CSS Styling
│   ├── Color Theme Variables
│   ├── Layout Styles
│   ├── Message Bubbles
│   ├── Input Area
│   └── Animations
└── JavaScript
    ├── API Integration
    ├── Message Management
    ├── File Handling
    ├── Gemini API Calls
    └── Tavily Search Integration
```

## API Functions

### Gemini Integration
- Sends conversation history to Google's Gemini API
- Handles tool calling for web search
- Manages multi-turn conversations with context

### Tavily Search
- Performs web searches when requested
- Returns top 5 results with answer synthesis
- Integrates results back into conversation flow

### File Processing
- Accepts any file type (images, documents, etc.)
- Encodes files to base64 for API transmission
- Displays file information and processing status

## Styling

The chatbot uses a sophisticated color scheme:

- **Background**: Deep purple-black (#0D0B14)
- **Primary Accent**: Purple (#8A2BE2)
- **Secondary Accent**: Cyan (#00BFFF)
- **Text**: Light gray (#E0E0E0)
- **Glowing Effects**: Animated shadows and borders

## Browser Compatibility

- Chrome/Chromium (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

## Limitations

- API keys are stored in browser memory only (not persisted)
- File size is limited by browser and API constraints
- Web search requires active internet connection
- Gemini API has its own rate limits and usage policies

## Security Notes

- Always keep your API keys confidential
- The HTML file runs entirely in the browser (client-side)
- API keys are never logged or stored permanently
- Use HTTPS when hosting on a server

## Troubleshooting

**"Error parsing JSON file"**: Ensure your API keys file is valid JSON with both "gemini" and "tavily" keys.

**"API Error"**: Check that your API keys are valid and have active quotas.

**"Search failed"**: Verify your Tavily API key is valid and you have search credits remaining.

**No response**: Check browser console for errors (F12 → Console tab).

## Future Enhancements

- Local storage for conversation history
- Customizable themes
- Multiple conversation threads
- Voice input/output support
- Custom system prompts
- Export conversation history

## License

This project is provided as-is under the MIT License.
