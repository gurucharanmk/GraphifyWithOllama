# NetworkX Demystified: A Beginner's Guide to Graph Theory

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This directory contains all code examples and resources for the "NetworkX Demystified" article series, providing a comprehensive introduction to graph theory and its implementation using the NetworkX library in Python.

## 📋 Table of Contents

- [Introduction](#introduction)
- [Core Concepts](#core-concepts)
- [Graph Algorithms](#graph-algorithms)
- [Knowledge Graph Introduction](#knowledge-graph-introduction)
- [Directory Structure](#directory-structure)
- [Prerequisites](#prerequisites)
- [Running the Examples](#running-the-examples)
- [Further Resources](#further-resources)

## 📝 Introduction

Graphs are powerful data structures that model relationships between entities. This article series and accompanying code examples provide a beginner-friendly approach to understanding and implementing graph theory concepts using NetworkX, a comprehensive Python library for creating, manipulating, and studying the structure and dynamics of complex networks.

## 🔍 Core Concepts

The series covers fundamental graph theory concepts with practical code examples:

### 1. Creating a Graph

Learn the basics of creating a graph structure with nodes and edges:

```python
import networkx as nx
import matplotlib.pyplot as plt

# Create an empty graph object
G = nx.Graph()

# Add nodes
G.add_node("A")
G.add_node("B")
G.add_node("C")

# Add edges
G.add_edge("A", "B")
G.add_edge("B", "C")

# Visualize the graph
plt.figure(figsize=(8, 6))
nx.draw(G, with_labels=True, node_color="lightblue", font_weight="bold")
plt.title("Basic Graph Creation")
plt.show()
```

### 2. Adding More Nodes and Edges

Extend your graph with additional nodes and connections:

```python
# Add more nodes
G.add_node("D")
G.add_node("E")

# Add more edges
G.add_edge("A", "D")
G.add_edge("C", "E")
G.add_edge("D", "E")
```

### 3. Directed Graphs (DiGraph)

Create graphs with directed relationships between nodes:

```python
# Create a directed graph
DG = nx.DiGraph()

# Add directed edges
DG.add_edge("A", "B")  # A -> B
DG.add_edge("B", "C")  # B -> C
```

### 4. Graph Visualization

Apply different layout algorithms to visualize graph structures:

```python
# Define layout for the graph 
pos = nx.spring_layout(G)

# Draw the graph with a specific layout
nx.draw(G, pos, with_labels=True)
```

## 🧮 Graph Algorithms

The series explores essential graph algorithms with practical implementations:

### 1. Shortest Path

Find the shortest path between nodes:

```python
shortest_path = nx.shortest_path(G, source="A", target="D")
```

### 2. Breadth-First Search (BFS)

Traverse a graph level by level:

```python
bfs_edges = list(nx.bfs_edges(G, source="A"))
```

### 3. Depth-First Search (DFS)

Explore as far as possible along branches before backtracking:

```python
dfs_edges = list(nx.dfs_edges(G, source="A"))
```

### 4. Degree of a Node

Calculate the number of connections a node has:

```python
degree_A = G.degree("A")
```

## 🧠 Knowledge Graph Introduction

The series introduces knowledge graphs as a practical application of graph theory:

```python
# Create a knowledge graph
KG = nx.Graph()

# Add entities (nodes)
KG.add_node("Albert Einstein")
KG.add_node("Theory of Relativity")
KG.add_node("Physics")
KG.add_node("E = mc^2")

# Add relationships (edges)
KG.add_edge("Albert Einstein", "Theory of Relativity", relationship="wrote")
KG.add_edge("Theory of Relativity", "Physics", relationship="is a concept of")
KG.add_edge("Albert Einstein", "E = mc^2", relationship="developed")
```

## 📂 Directory Structure

```
networkx_demystified/
├── README.md                       # This file
├── examples/                       # Example scripts
│   ├── 01_basic_graph_creation.py  # Creating simple graphs
│   ├── 02_adding_nodes_edges.py    # Adding nodes and edges to graph
│   ├── 03_directed_graphs.py       # Create directed graph
│   ├── 04_graph_visualization.py   # Visualize graph
│   ├── 05_shortest_path.py         # Finding shortest path between nodes
│   ├── 06_bfs_traversal.py         # BFS
│   ├── 07_dfs_traversal.py         # DFS
│   ├── 08_node_degree.py           # Degree of a node
│   └── 09_knowledge_graph.py       # Simple knowledge graph example
└── images/                         # Generated graph visualizations
```

## 🔧 Prerequisites

To run the examples in this series, you'll need:

- Python 3.12+
- NetworkX
- Matplotlib

Install the required packages:

```bash
pip install networkx matplotlib
```

## 🚀 Running the Examples

Each example file can be run directly:

```bash
python examples/01_basic_graph_creation.py
```

Alternatively, you can run the code snippets in a Jupyter notebook or any Python environment.

## 📚 Further Resources

- [NetworkX Documentation](https://networkx.org/documentation/stable/)
- [Graph Theory Basics](https://en.wikipedia.org/wiki/Graph_theory)
- [Knowledge Graph Overview](https://en.wikipedia.org/wiki/Knowledge_graph)

---

Happy graphing! This article series aims to make graph theory accessible and practical for beginners.
