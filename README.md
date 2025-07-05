# Stockbroker - Using LangChain and LangGraph

A full-stack stockbroker and financial analyst application built with LangGraph.js, featuring generative UI components and Human-in-the-Loop (HITL) functionality for stock transactions.

## Overview

This project demonstrates how to build an intelligent stockbroker agent using LangGraph.js. The application provides real-time stock information, portfolio management, and interactive stock purchasing capabilities with a modern, responsive UI.

# Interface 
![image](https://github.com/user-attachments/assets/e1eaf050-1449-414b-a235-770106d92ace)

# Langsmith working
![image](https://github.com/user-attachments/assets/04324b49-4d13-4dd7-945d-18075f51d0d5)

## Features

- **Real-time Stock Prices**: Query current stock prices by company name or ticker symbol
- **Stock Purchasing**: Interactive UI for buying stocks with HITL approval
- **Portfolio Management**: View and manage your stock portfolio
- **Generative UI Components**: Dynamic UI elements generated based on user interactions
- **Agent-based Architecture**: Built using LangGraph.js for orchestrating complex workflows

## Prerequisites

- Node.js 18+ 
- npm or yarn
- OpenAI API key
- Google GenAI API key (optional but recommended)
- Financial Datasets API key (for real stock data)

## Project Structure

```
stockbroker/
├── backend/
│   ├── src/
│   │   ├── index.ts        # Main backend entry point
│   │   ├── agent.ts        # Stockbroker agent implementation
│   │   └── tools/          # Agent tools for stock operations
│   ├── package.json
│   └── tsconfig.json
├── frontend/
│   ├── src/
│   │   ├── App.tsx         # Main React application
│   │   ├── components/     # UI components
│   │   └── hooks/          # Custom React hooks
│   ├── package.json
│   └── vite.config.ts
└── README.md
```

## Installation

1. Clone the repository:
```bash
git clone https://github.com/bracesproul/langgraphjs-examples.git
cd langgraphjs-examples/stockbroker
```

2. Install backend dependencies:
```bash
cd backend
npm install
```

3. Install frontend dependencies:
```bash
cd ../frontend
npm install
```

## Configuration

1. Create a `.env` file in the backend directory:

```env
# Required
OPENAI_API_KEY="your-openai-api-key"
GOOGLE_API_KEY="your-google-api-key"

# Required for stock data
FINANCIAL_DATASETS_API_KEY="your-financial-datasets-api-key"

# Optional - for tracing and observability
LANGSMITH_PROJECT="stockbroker-agent"
LANGSMITH_API_KEY="your-langsmith-api-key"
LANGSMITH_TRACING_V2=true
```

2. Configure frontend environment variables (if needed):
```env
VITE_API_URL="http://localhost:3000"
```

## Running the Application

### Development Mode

1. Start the backend server:
```bash
cd backend
npm run dev
```

2. In a new terminal, start the frontend:
```bash
cd frontend
npm run dev
```

3. Open your browser and navigate to `http://localhost:5173`

### Production Build

1. Build the backend:
```bash
cd backend
npm run build
```

2. Build the frontend:
```bash
cd frontend
npm run build
```

3. Start the production server:
```bash
cd backend
npm start
```

## Usage

### Example Interactions

1. **Check Stock Price**:
   - "What's the current price of Apple?"
   - "Show me TSLA stock price"

2. **Buy Stocks**:
   - "I want to buy 10 shares of Microsoft"
   - "Purchase 5 shares of GOOGL"

3. **View Portfolio**:
   - "Show me my portfolio"
   - "What stocks do I own?"

### How It Works

1. **User Input**: Users interact with the chat interface to make requests
2. **Agent Processing**: The LangGraph.js agent processes the request and determines the appropriate action
3. **Tool Execution**: Specific tools are called to fetch stock data or execute transactions
4. **UI Generation**: Dynamic UI components are generated based on the action
5. **Human Approval**: For stock purchases, users must approve the transaction (HITL)
6. **Confirmation**: Transaction results are displayed with updated portfolio information

## API Endpoints

### Backend API

- `POST /api/chat` - Main chat endpoint for agent interactions
- `GET /api/portfolio` - Retrieve user portfolio
- `POST /api/transaction` - Execute stock transactions
- `GET /api/stock/:ticker` - Get stock information

## Architecture

The application uses a modern architecture with:

- **Backend**: Node.js with TypeScript, Express.js, and LangGraph.js
- **Frontend**: React with TypeScript and Vite
- **State Management**: LangGraph.js for agent state orchestration
- **AI Integration**: OpenAI for natural language processing
- **Stock Data**: Financial Datasets API for real-time stock information

## Development

### Adding New Tools

To add new tools to the stockbroker agent:

1. Create a new tool file in `backend/src/tools/`
2. Implement the tool interface
3. Register the tool in the agent configuration
4. Update the frontend to handle new UI components if needed

### Testing

Run tests with:
```bash
npm test
```

## Troubleshooting

### Common Issues

1. **API Key Errors**: Ensure all required API keys are properly set in the `.env` file
2. **Port Conflicts**: Make sure ports 3000 (backend) and 5173 (frontend) are available
3. **Stock Data Issues**: Verify your Financial Datasets API key has proper permissions

### Debug Mode

Enable debug logging by setting:
```env
DEBUG=stockbroker:*
```

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is part of the LangGraph.js examples repository. See the main repository for license information.

## Acknowledgments

- Built with [LangGraph.js](https://github.com/langchain-ai/langgraphjs)
- Part of the [LangGraph.js Examples](https://github.com/bracesproul/langgraphjs-examples) collection
- Inspired by modern fintech applications

## Resources

- [LangGraph.js Documentation](https://langchain-ai.github.io/langgraphjs/)
- [LangChain Documentation](https://js.langchain.com/)
- [Financial Datasets API](https://financialdatasets.ai/)

## Support

For issues and questions:
- Open an issue in the [GitHub repository](https://github.com/bracesproul/langgraphjs-examples/issues)
- Check the [LangGraph.js community](https://github.com/langchain-ai/langgraphjs/discussions)
