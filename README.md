# 🤖🧠 Visual AI Automation Builder

A visual, no-code platform for creating AI-powered workflows inspired by n8n. Build, visualize, and execute complex LLM-driven automation pipelines using a simple, intuitive interface.

![Visual AI Automation Builder](https://github.com/yourusername/AI-Automation-Builder/assets/youruid/ai-automation-builder-screenshot.png)

## 🌟 Features

- **Visual Workflow Editor**: Design automation workflows using a visual, node-based interface
- **LLM-Powered Nodes**: Each node uses GPT-4o to perform specific tasks in your workflow
- **Web Search Integration**: Nodes can search the web to retrieve up-to-date information
- **Dynamic Routing**: Route workflow execution based on LLM output decisions
- **Pre-built Templates**: Start quickly with ready-to-use workflow templates
- **Real-time Execution**: Watch as your workflow executes step by step
- **Streamlit Interface**: User-friendly interface built with Streamlit

## 📋 Requirements

- Python 3.8+
- OpenAI API Key

## 🚀 Quick Start

### Installation

1. Clone the repository:

```bash
git clone https://github.com/yourusername/AI-Automation-Builder.git
cd "AI Automation Builder"
```

2. Install dependencies:

```bash
pip install -r requirements_visual_builder.txt
```

### Running the Application

1. Set your OpenAI API key as an environment variable:

```bash
# On macOS/Linux
export OPENAI_API_KEY=your-api-key

# On Windows
set OPENAI_API_KEY=your-api-key
```

2. Launch the app:

```bash
streamlit run n8n_kinda.py
```

3. Open your browser and navigate to the URL shown in the terminal (typically `http://localhost:8501`).

## 🔧 Usage Guide

### Creating a Workflow

1. **Add Nodes**: Use the "Node Palette" in the sidebar to add new nodes to your workflow
2. **Configure Nodes**: Click on any node to edit its name, prompt, and routing logic
3. **Connect Nodes**: Set up routing rules to determine how data flows between nodes

### Node Configuration

Each node requires:
- **Name**: A descriptive name for the node
- **Prompt**: Instructions for the LLM to execute
- **Routing Rules**: 
  - Default target (where to go if no specific key is found)
  - Conditional targets (routes based on output keys)

### Executing a Workflow

1. Click "Compile Workflow" to prepare the workflow for execution
2. Enter an initial input message in the "Execute Workflow" section
3. Click "Run Workflow" to execute
4. View results in the "Execution Results" section

## 🧩 Example Workflows

The application includes several pre-built workflow templates:

- **Summarizer**: Simple text summarization workflow
- **Sentiment**: Analyzes sentiment and provides tailored responses
- **Classification**: Classifies user inputs into categories with specific handling
- **Deep Research**: Multi-step research process with cross-referencing
- **Advanced Hedge Fund**: Complex financial analysis and portfolio recommendation

## 🏗️ Architecture

The application uses:
- **LangGraph**: For defining and executing the workflow graph
- **LangChain**: For integrating with LLMs and tools
- **Streamlit**: For the web interface
- **Streamlit-Agraph**: For workflow visualization

## 📝 Key Concepts

- **Nodes**: Individual steps in the workflow, each powered by an LLM
- **Routing Keys**: Special markers returned by nodes to determine the next step
- **State**: Dictionary containing the workflow's current state and history

## 🔄 Workflow State

Each workflow maintains a state dictionary with:
- `input`: The initial user input
- `node_outputs`: Outputs from each node
- `last_response_content`: The most recent node output
- `current_node_id`: ID of the currently executing node

## 🧰 Advanced Usage

### Custom Prompts

Node prompts can include the `{input_text}` placeholder to insert previous content:

```
Analyze the sentiment of this text: {input_text}
```

### Routing Logic

Nodes should end their responses with a routing key:

```
ROUTING_KEY: positive
```

This determines which node receives the output next.

## ⚠️ Limitations

- Web search functionality requires OpenAI's gpt-4o model
- Complex workflows may hit execution limits
- LLM outputs can be unpredictable; test thoroughly

## 🤝 Contributing

Contributions welcome! Please:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- Inspired by [n8n](https://n8n.io/)
- Built with [Streamlit](https://streamlit.io/)
- LLM functionality powered by [OpenAI](https://openai.com/)
- Graph execution by [LangGraph](https://github.com/langchain-ai/langgraph)

## 👤 Author

Your Name - [GitHub](https://github.com/yourusername)
