# Transform Data into Knowledge: Creating Graphs with Ollama

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This directory contains the code and resources for the "Transform Data into Knowledge" article series, demonstrating how to extract entities and relationships from unstructured text using Ollama LLMs and convert them into knowledge graphs with NetworkX.

## 📋 Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Directory Structure](#directory-structure)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
  - [Basic Usage](#basic-usage)
  - [Custom Prompts](#custom-prompts)
  - [Visualization Options](#visualization-options)
- [Process Pipeline](#process-pipeline)
- [Example Results](#example-results)
- [Troubleshooting](#troubleshooting)
- [Advanced Customization](#advanced-customization)

## 📝 Introduction

Knowledge graphs represent information as a network of entities and relationships, providing a powerful way to organize, query, and derive insights from data. This article series and accompanying code demonstrate how to:

1. Extract structured information from unstructured text using Ollama LLMs
2. Transform these extractions into graph structures with NetworkX
3. Visualize and analyze the resulting knowledge graphs

## ✨ Features

- **Text to Knowledge Graph Conversion**: Transform any text document into a structured knowledge graph
- **Entity and Relationship Extraction**: Automatically identify entities and their relationships in text
- **Customizable Prompts**: Tailor the extraction process for different domains and use cases
- **Interactive Visualization**: Create insightful graph visualizations with NetworkX and Matplotlib
- **Easy Integration**: Simple API that works with locally running Ollama models

## 📂 Directory Structure

```
knowledge_graphs_with_ollama/
├── README.md                      # This file
├── examples/                      # Example implementations
│   ├── knowledge_graph_processor.py  # Main processor class
│   └── sample_data/               # Example text documents
│       └── mel_gibson.txt         # Sample biographical text
└── images/                        # Generated knowledge graph visualizations
```

## 🔧 Prerequisites

To run the examples in this series, you'll need:

- Python 3.8+
- NetworkX
- Matplotlib
- OpenAI Python package (for API compatibility with Ollama)
- Ollama running locally or accessible via API

## 📦 Installation

1. Make sure you have Ollama installed and running:
   ```bash
   # Install Ollama following instructions at https://ollama.ai/
   # Run a model (Llama 3.2 recommended)
   ollama run llama3.2
   ```

2. Install the required Python packages:
   ```bash
   pip install networkx matplotlib openai
   ```

## 🚀 Usage

### Basic Usage

```python
# Initialize the processor with default settings
processor = KnowledgeGraphProcessor(model="llama3.2")

# Process a text document
with open("sample_data/mel_gibson.txt", "r") as f:
    text = f.read()

# Extract entities and relationships, build and visualize the graph
G, json_output = processor.process_text(text, title="Mel Gibson Knowledge Graph")
```

### Custom Prompts

You can customize the system and user prompts to tailor the extraction for specific domains:

```python
processor = KnowledgeGraphProcessor(model="llama3.2")

# Set custom system prompt
processor.set_system_prompt("""You are a film industry expert. Extract entities and relationships 
related to movies, actors, directors, and film studios from the text...""")

# Set custom user prompt template
processor.set_user_prompt_template("""Extract film industry entities and relationships 
from the following text: "{text}"...""")

# Process text with custom prompts
G, json_output = processor.process_text(text)
```

### Visualization Options

The default visualization uses NetworkX with Matplotlib. You can customize the visualization by extending the `visualize_graph` method:

```python
# Customize node colors based on entity types
node_colors = {
    'person': 'skyblue',
    'film': 'lightgreen',
    'award': 'gold',
    'organization': 'lightpink'
}

# Create processor and process text
processor = KnowledgeGraphProcessor()
G, json_output = processor.process_text(text)
```

## 🔄 Process Pipeline

The knowledge graph creation process follows these steps:

1. **Text Input**: Unstructured text document is provided
2. **Entity and Relationship Extraction**: 
   - Text is sent to Ollama LLM via API
   - LLM extracts entities and relationships, returning JSON
3. **Graph Construction**:
   - JSON is parsed into NetworkX graph structure
   - Entities become nodes with type attributes
   - Relationships become directed edges with labels
4. **Visualization and Analysis**:
   - Graph is visualized with appropriate layouts and styling
   - Basic statistics and insights can be calculated

## 📊 Example Results

When processing a biographical text about Mel Gibson, the processor extracts entities such as:
- People (Mel Gibson, George Miller)
- Films (Mad Max, Braveheart)
- Organizations (NIDA, Academy Awards)
- Locations (Peekskill, Sydney)

And relationships like:
- "starred_in" (Mel Gibson → Mad Max)
- "directed" (Mel Gibson → Braveheart)
- "won" (Braveheart → Academy Award)

## ❓ Troubleshooting

**Common issues and solutions:**

1. **Ollama Connection Issues**:
   - Ensure Ollama is running locally (`ollama list` to verify)
   - Check the base URL is correct (default: http://localhost:11434/v1)

2. **JSON Parsing Errors**:
   - LLM might return malformed JSON; check raw output with debug print
   - Try adjusting temperature parameter for more consistent outputs

3. **Graph Visualization Issues**:
   - For large graphs, try different layout algorithms (spring_layout, kamada_kawai_layout)
   - Adjust node spacing with the `k` parameter in layout functions

## 🛠️ Advanced Customization

The `KnowledgeGraphProcessor` class can be extended or modified for advanced use cases:

- Implement more sophisticated graph analysis methods
- Add export functions for graph databases (Neo4j, etc.)
- Create domain-specific extraction patterns with custom prompts
- Integrate with other LLMs or services beyond Ollama

---

Transform your unstructured data into structured, actionable knowledge with this approach!
