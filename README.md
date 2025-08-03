# Confluence AI Assistant

A powerful AI-powered assistant that integrates with Confluence to provide intelligent search, analysis, and automation capabilities. This application helps teams extract insights from their Confluence documentation, analyze code changes, generate test strategies, and automate various documentation tasks.

## 🚀 Features

### Core AI Features
- **AI-Powered Search**: Intelligent search across Confluence pages with context-aware responses
- **Video Summarizer**: Extract insights from video content using AssemblyAI transcription
- **Code Assistant**: Analyze, modify, and convert code between different programming languages
- **Impact Analyzer**: Assess the impact of code changes with risk analysis and recommendations
- **Document Analysis**: Evaluate documentation quality across maintainability, usability, accessibility, and consistency
- **Test Support Tool**: Generate comprehensive test strategies and cross-platform testing plans

### Export & Integration Features
- **Multi-Format Export**: Export content to PDF, DOCX, PPTX, CSV, JSON, HTML, and TXT formats
- **Confluence Integration**: Save analysis results directly to Confluence pages
- **GitHub Actions Integration**: Automatically generate CI/CD workflows and test configurations
- **Jira & Slack Integration**: Push tasks and notifications to Jira and Slack

### Advanced Features
- **Image Insights**: Analyze images and extract insights using AI
- **Chart Generation**: Create visual charts from data tables and Excel files
- **Voice Recording**: Voice-to-text input for questions and queries
- **Agent Mode**: Goal-based analysis across multiple Confluence spaces

## 🛠️ Technology Stack

### Backend
- **FastAPI**: Modern Python web framework for building APIs
- **Google Gemini AI**: Advanced AI model for natural language processing
- **Atlassian Python API**: Confluence integration
- **FPDF2**: PDF generation
- **python-docx**: Word document generation
- **python-pptx**: PowerPoint presentation generation
- **AssemblyAI**: Video transcription and analysis
- **Matplotlib/Seaborn**: Chart generation

### Frontend
- **React 18**: Modern React with TypeScript
- **Vite**: Fast build tool and development server
- **Tailwind CSS**: Utility-first CSS framework
- **Chart.js**: Interactive charts and visualizations
- **React Router**: Client-side routing

### Infrastructure
- **Render**: Cloud hosting platform
- **Environment Variables**: Secure configuration management

## 📋 Prerequisites

Before running this application, ensure you have:

- **Python 3.8+** installed
- **Node.js 16+** installed
- **Git** for version control
- Access to the following services:
  - Confluence instance
  - Google Gemini AI API
  - AssemblyAI API (for video features)
  - GitHub (for GitHub Actions integration)
  - Jira (optional, for task integration)
  - Slack (optional, for notifications)

## 🔧 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/confluence-ai-assistant.git
cd confluence-ai-assistant
```

### 2. Backend Setup

```bash
cd UI-main/backend

# Create virtual environment
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

### 3. Frontend Setup

```bash
cd UI-main

# Install dependencies
npm install

# Build the application
npm run build
```

### 4. Environment Configuration

Create a `.env` file in the `UI-main/backend` directory:

```env
# Confluence Configuration
CONFLUENCE_BASE_URL=https://your-domain.atlassian.net
CONFLUENCE_USER_EMAIL=your-email@domain.com
CONFLUENCE_API_KEY=your-confluence-api-key

# AI Configuration
GENAI_API_KEY_1=your-gemini-api-key-1
GENAI_API_KEY_2=your-gemini-api-key-2

# AssemblyAI (for video features)
ASSEMBLYAI_API_KEY=your-assemblyai-api-key

# Optional: Google Search API
GOOGLE_API_KEY=your-google-api-key
SEARCH_ENGINE_ID=your-search-engine-id

# Optional: Stack Overflow API
STACK_OVERFLOW_API_KEY=your-stack-overflow-api-key

# Optional: Jira Integration
JIRA_BASE_URL=https://your-domain.atlassian.net
JIRA_EMAIL=your-email@domain.com
JIRA_API_TOKEN=your-jira-api-token

# Optional: Slack Integration
SLACK_TOKEN=your-slack-bot-token
```

## 🚀 Running the Application

### Development Mode

#### Backend
```bash
cd UI-main/backend
uvicorn main:app --reload --host 0.0.0.0 --port 8000
```

#### Frontend
```bash
cd UI-main
npm run dev
```

The application will be available at:
- Frontend: http://localhost:5173
- Backend API: http://localhost:8000

### Production Deployment

#### Using Render

1. **Backend Deployment**:
   - Connect your GitHub repository to Render
   - Create a new Web Service
   - Set the build command: `pip install -r requirements.txt`
   - Set the start command: `uvicorn main:app --host 0.0.0.0 --port $PORT`
   - Add all environment variables from your `.env` file

2. **Frontend Deployment**:
   - Create a new Static Site in Render
   - Set the build command: `npm install && npm run build`
   - Set the publish directory: `dist`
   - Configure environment variables for API endpoints

## 📖 Usage Guide

### Getting Started

1. **Configure API Keys**: Set up your environment variables with the required API keys
2. **Connect to Confluence**: The app will automatically detect your Confluence spaces
3. **Select a Tool**: Choose from the available AI-powered tools in the interface
4. **Analyze Content**: Use the tools to extract insights, analyze code, or generate reports
5. **Export Results**: Download results in your preferred format (PDF, DOCX, etc.)

### Available Tools

#### AI-Powered Search
- Search across multiple Confluence pages
- Get context-aware responses based on your documentation
- Ask follow-up questions for deeper insights

#### Video Summarizer
- Upload video files to Confluence pages
- Get automatic transcription and summarization
- Extract key quotes and timestamps
- Ask specific questions about video content

#### Code Assistant
- Analyze code from Confluence pages
- Modify code based on instructions
- Convert code between programming languages
- Generate code summaries and explanations

#### Impact Analyzer
- Compare different versions of code or documentation
- Get detailed impact analysis with risk assessment
- Receive recommendations for improvements
- Check for potential issues using Stack Overflow data

#### Test Support Tool
- Generate comprehensive test strategies
- Create cross-platform testing plans
- Analyze test data sensitivity
- Generate GitHub Actions workflows

#### Document Analysis
- Evaluate documentation quality
- Assess maintainability, usability, accessibility, and consistency
- Get actionable recommendations for improvement

## 🔌 API Endpoints

### Core Endpoints
- `GET /spaces` - Get available Confluence spaces
- `GET /pages/{space_key}` - Get pages from a specific space
- `POST /search` - AI-powered search across pages
- `POST /export` - Export content in various formats

### Feature-Specific Endpoints
- `POST /video-summarizer` - Video analysis and summarization
- `POST /code-assistant` - Code analysis and modification
- `POST /impact-analyzer` - Change impact analysis
- `POST /test-support` - Test strategy generation
- `POST /analyze-document` - Document quality analysis
- `POST /github-actions-integration` - GitHub Actions workflow generation

### Integration Endpoints
- `POST /save-to-confluence` - Save content to Confluence
- `POST /push-to-jira-confluence-slack` - Push tasks to Jira and Slack
- `POST /create-chart` - Generate charts from data
- `POST /image-summary` - Analyze images with AI

## 🏗️ Project Structure

```
confluence-ai-assistant/
├── UI-main/
│   ├── backend/
│   │   ├── main.py              # FastAPI application
│   │   ├── requirements.txt     # Python dependencies
│   │   ├── runtime.txt          # Python runtime version
│   │   └── render.yaml          # Render deployment config
│   ├── src/
│   │   ├── components/          # React components
│   │   │   ├── AIPoweredSearch.tsx
│   │   │   ├── CodeAssistant.tsx
│   │   │   ├── ImpactAnalyzer.tsx
│   │   │   ├── VideoSummarizer.tsx
│   │   │   └── ...
│   │   ├── services/
│   │   │   └── api.ts           # API service layer
│   │   ├── utils/               # Utility functions
│   │   └── App.tsx              # Main application component
│   ├── package.json             # Node.js dependencies
│   ├── vite.config.ts           # Vite configuration
│   └── tailwind.config.js       # Tailwind CSS configuration
├── README.md                    # This file
└── .gitignore                   # Git ignore rules
```

## 🔒 Security Considerations

- **API Keys**: Never commit API keys to version control
- **Environment Variables**: Use environment variables for all sensitive configuration
- **CORS**: Configure CORS settings appropriately for your deployment
- **Rate Limiting**: Implement rate limiting for production deployments
- **Input Validation**: All user inputs are validated and sanitized

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Guidelines

- Follow the existing code style and conventions
- Add appropriate error handling and logging
- Write tests for new features
- Update documentation for any API changes
- Ensure all environment variables are documented

## 🐛 Troubleshooting

### Common Issues

1. **PDF Export Not Working**
   - Ensure FPDF2 is properly installed
   - Check that the content doesn't contain unsupported characters
   - Verify the export endpoint is receiving valid requests

2. **Confluence Connection Issues**
   - Verify your Confluence API credentials
   - Check that your Confluence instance is accessible
   - Ensure you have the necessary permissions

3. **AI Model Errors**
   - Verify your Gemini API keys are valid
   - Check your API quota and limits
   - Ensure the API keys have the necessary permissions

4. **Frontend Build Issues**
   - Clear node_modules and reinstall dependencies
   - Check for TypeScript compilation errors
   - Verify all required environment variables are set

### Debug Endpoints

The application includes several debug endpoints for troubleshooting:

- `GET /test` - Basic API health check
- `GET /debug-attachments/{space_key}/{page_title}` - Debug attachment retrieval
- `GET /debug-document-analysis/{space_key}/{page_title}` - Debug document analysis

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Google Gemini AI** for providing the AI capabilities
- **Atlassian** for the Confluence API
- **AssemblyAI** for video transcription services
- **FastAPI** for the excellent web framework
- **React** and **Vite** for the frontend tooling

## 📞 Support

For support and questions:

- Create an issue in the GitHub repository
- Check the troubleshooting section above
- Review the API documentation in the code comments

## 🔄 Version History

- **v1.0.0** - Initial release with core AI features
- **v1.1.0** - Added video summarizer and chart generation
- **v1.2.0** - Enhanced export functionality and GitHub Actions integration
- **v1.3.0** - Added document analysis and improved error handling

---

**Note**: This application requires valid API keys and access to the respective services. Make sure to review the pricing and usage limits for each service before deploying to production.

---

**Developed by Team Word Wizards** 