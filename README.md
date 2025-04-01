# GraphifyWithOllama

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A comprehensive toolkit for building, analyzing, and visualizing knowledge graphs using NetworkX and Ollama. This repository contains the code and examples for two article series:

1. **NetworkX Demystified**: A beginner's guide to graph theory and implementation using NetworkX
2. **Transform Data into Knowledge**: Create knowledge graphs from unstructured text using Ollama LLMs

## 📋 Table of Contents

- [Overview](#overview)
- [Repository Structure](#repository-structure)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Series Contents](#series-contents)
- [Usage Examples](#usage-examples)
- [License](#license)
- [Contact](#contact)


## 🔍 Overview

GraphifyWithOllama provides practical tools and examples for working with graph data structures, particularly knowledge graphs. The repository demonstrates how to:

- Create and manipulate graphs using the NetworkX library
- Apply graph theory algorithms to solve common problems
- Extract entities and relationships from unstructured text using Ollama
- Build and visualize knowledge graphs from text documents
- Perform graph analysis to derive insights from connected data

Whether you're a beginner learning graph theory or a practitioner looking to implement knowledge graphs with LLMs, this repository offers code, examples, and tutorials to help you get started.

## 📂 Repository Structure

```
GraphifyWithOllama/
├── README.md                      # Main repository README
├── requirements.txt               # Project dependencies
├── networkx_demystified/          # Article 1 content
│   ├── README.md                  # NetworkX tutorial README
│   ├── examples/                  # Example graph scripts
│   │   ├── 01_basic_graph_creation.py
│   │   ├── 02_adding_nodes_edges.py
│   │   ├── 03_directed_graphs.py
│   │   ├── 04_graph_visualization.py
│   │   └── 05_shortest_path.py
│   │   └── 06_bfs_traversal.py
│   │   └── 07_dfs_traversal.py
│   │   └── 08_node_degree.py
│   │   └── 09_knowledge_graph.py
│   └── images/                    # Generated graph visualizations
├── knowledge_graphs_with_ollama/  # Article 2 content
│   ├── README.md                  # Knowledge graph with Ollama README
│   ├── examples/                  # Example implementations
│   │   ├── knowledge_graph_processor.py
│   │   └── sample_data/
│   │       └── mel_gibson.txt
│   └── images/                    # Generated knowledge graph visualizations
└── LICENSE                        # MIT License file
```

## 🚀 Getting Started

### Prerequisites

- Python 3.12+
- NetworkX
- Matplotlib
- OpenAI Python package (for Ollama API compatibility)
- Ollama (running locally or accessible via API)

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/gurucharanmk/GraphifyWithOllama.git
   cd GraphifyWithOllama
   ```

2. Install the required dependencies in your virtual env:
   ```bash
   pip install -r requirements.txt
   ```

3. For Ollama integration, make sure you have Ollama installed and running:
   ```bash
   # Install Ollama following instructions at https://ollama.ai/
   # Run a model (Llama 3.2 recommended)
   ollama run llama3.2
   ```

## 📚 Series Contents

### Article 1: NetworkX Demystified - A Beginner's Guide to Graph Theory

- Core graph concepts
- Creating and manipulating graphs
- Directed vs. undirected graphs
- Graph visualization techniques
- Basic graph algorithms (BFS, DFS, shortest path)
- Node degree and centrality
- Introduction to knowledge graphs

### Article 2: Transform Data into Knowledge - Creating Graphs with Ollama

- Extracting entities and relationships from text
- Building knowledge graph structures
- Entity and relationship visualization
- Graph querying and analysis
- Real-world knowledge graph applications

## 💻 Usage Examples

### Basic Graph Creation with NetworkX

```python
import networkx as nx
import matplotlib.pyplot as plt

# Create a simple graph
G = nx.Graph()
G.add_nodes_from(["A", "B", "C"])
G.add_edges_from([("A", "B"), ("B", "C")])

# Visualize
plt.figure(figsize=(6, 4))
nx.draw(G, with_labels=True, node_color="lightblue", font_weight="bold")
plt.title("Simple Graph")
plt.show()
```

### Knowledge Graph Creation with Ollama

```python
# Initialize processor
processor = KnowledgeGraphProcessor(model="llama3.2")

# Process text
with open("sample_data/mel_gibson.txt", "r") as f:
    text = f.read()

# Extract entities and relationships, build and visualize graph
G, json_output = processor.process_text(text, title="Mel Gibson Knowledge Graph")
```

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 📧 Contact

For questions or feedback, please open an issue or reach out directly.

---

Happy graphing!
