
# Graph Search System Using BFS and DFS

## SLE-4: Architecture Decision Record (ADR)

### Project Information

- **Course:** 02AML204 – Introduction to Artificial Intelligence
- **PRN:** 25UAM049
- **Student Name:** Gouri Rajendra Kudalkar
- **Division:** A
- **Project Title:** Graph Search System Using BFS and DFS
- **ADR Title:** Modular Architecture for the BFS and DFS Graph Search System
- **ADR Status:** Accepted
- **ADR Date:** 11 October 2026

## 1. Project Overview

The Graph Search System is an Artificial Intelligence project that implements and compares two uninformed search algorithms: Breadth-First Search (BFS) and Depth-First Search (DFS).

The system uses a graph containing 800 nodes, with node 0 as the starting node and node 799 as the goal node. It measures execution time, counts the number of expanded nodes, and records whether the goal is found.

The project focuses on algorithmic performance analysis and modular software architecture.

## 2. Objectives

- Implement BFS and DFS for graph searching.
- Compare the performance of both algorithms.
- Measure execution time and expanded nodes.
- Understand the differences between queue-based and stack-based search.
- Design the system using the complete C4 architecture model.
- Document the architectural decision using an Architecture Decision Record (ADR).

## 3. Algorithms Used

### Breadth-First Search (BFS)

BFS explores the graph level by level. It uses a queue to manage the nodes waiting to be explored.

**Key points:**
- Uses a First-In, First-Out (FIFO) queue.
- Explores nearby nodes before deeper nodes.
- Finds the shortest path in an unweighted graph when implemented with standard BFS.

### Depth-First Search (DFS)

DFS explores one path as deeply as possible before backtracking. It uses a stack or recursion to manage the search.

**Key points:**
- Uses a Last-In, First-Out (LIFO) stack.
- Explores deeper paths first.
- Does not guarantee the shortest path in a general graph.

## 4. SLE-2: Empirical Performance Analysis

In SLE-2, BFS and DFS were evaluated on a graph containing 800 nodes.

### Experimental Setup

| Parameter | Value |
|---|---|
| Graph size | 800 nodes |
| Start node | 0 |
| Goal node | 799 |
| Performance metrics | Execution time and nodes expanded |
| Goal found | Yes, for both algorithms |

### Performance Comparison

| Metric | BFS | DFS |
|---|---:|---:|
| Best execution time | 175.03617 ms | 186.90420 ms |
| Average execution time | 191.69571 ms | 203.76627 ms |
| Worst execution time | 217.95790 ms | 232.18527 ms |
| Nodes expanded | 800 | 800 |
| Goal found | Yes | Yes |

### Observation

BFS recorded a lower average execution time than DFS in the reported experiment. Both algorithms expanded 800 nodes and successfully found the goal.

These results apply to the tested graph and execution conditions. Performance may vary with graph structure, implementation, and runtime conditions.

## 5. SLE-3: Full C4 Architecture Model

The system architecture was designed using four levels of the C4 model.

### Level 1: System Context

Shows the interaction between the user and the Graph Search System.

### Level 2: Container

Shows the major parts of the system, including input handling, graph management, search execution, performance measurement, and output.

### Level 3: Component

Explains the responsibilities of the internal components, including BFS, DFS, visited-node management, and performance measurement.

### Level 4: Code

Describes how the architecture is represented through code-level functions, data structures, and algorithm implementations.

### Main System Modules

- **Input Module:** Accepts graph and search configuration.
- **Graph Management Module:** Creates and maintains the graph representation.
- **Search Engine:** Executes BFS and DFS.
- **Visited/Memory Management:** Tracks visited nodes and helps prevent repeated exploration.
- **Performance Measurement:** Records execution time and search statistics.
- **Output Module:** Displays the search results and performance measurements.

### Architecture Diagrams

The C4 diagrams should be added to this repository and displayed below.

#### 1. System Context Diagram

![System Context Diagram](./images/context-diagram.png)

#### 2. Container Diagram

![Container Diagram](./images/container-diagram.png)

#### 3. Component Diagram

![Component Diagram](./images/component-diagram.png)

#### 4. Code Diagram

![Code Diagram](./images/code-diagram.png)

**Note:** Store the actual diagram image files in the `images` folder using the filenames shown above. Replace the filenames in this README if your files use different names.

## 6. Architecture Decision Record (ADR)

### ADR Title

Modular Architecture for the BFS and DFS Graph Search System

### Context

The system needs to implement and compare BFS and DFS while measuring their performance. Both algorithms operate on the same graph but use different search strategies.

### Decision

A modular architecture was selected to separate graph representation, search algorithms, visited-node management, performance measurement, and output.

BFS uses a queue, whereas DFS uses a stack. The common graph representation can be reused by both algorithms.

### Alternatives Considered

1. **BFS only:** Simple level-by-level exploration, but no direct comparison with DFS.
2. **DFS only:** Supports depth-oriented exploration, but no direct comparison with BFS.
3. **Modular BFS and DFS architecture:** Supports independent implementation, testing, and comparison.

The third alternative was selected because it provides better organization, readability, and maintainability.

### Rationale

The SLE-2 results showed that BFS had a lower average execution time than DFS for the tested graph. Both algorithms found the goal and expanded the same number of nodes.

The SLE-3 C4 architecture supports the decision by separating the major responsibilities into understandable modules.

### Consequences

**Positive consequences:**
- Algorithms can be tested independently.
- Graph representation can be reused.
- Components are easier to understand and maintain.
- Performance results can be compared consistently.

**Trade-offs:**
- Separate implementations require additional code.
- Execution times can vary between runs.
- Results from one graph may not generalize to every graph.
- Larger graphs may require additional memory and processing time.

## 7. SLE Journey: SLE-1 to SLE-4

- **SLE-1:** Worked on the AI project and its implementation.
- **SLE-2:** Compared BFS and DFS using empirical performance analysis.
- **SLE-3:** Designed the system architecture using the four C4 levels.
- **SLE-4:** Documented and justified the modular architecture decision using experimental results and architectural analysis.

## 8. Technologies and Concepts

- Python
- Graph representation
- Breadth-First Search (BFS)
- Depth-First Search (DFS)
- Queue and stack data structures
- Performance profiling
- Execution-time measurement
- C4 software architecture model
- Architecture Decision Record (ADR)
- Git and GitHub

## 9. AI Contribution

**AI Tool Used:** ChatGPT

**AI Contribution:** Assisted in understanding the ADR structure, BFS and DFS concepts, performance analysis, C4 architecture, and organization of project documentation.

**Student Contribution:** Project implementation, performance analysis, review of experimental results, architecture diagram preparation, and verification of the final documentation.

## 10. GitHub Repositories

- **SLE-2:** https://github.com/kudalkargouri-crypto/IAI_SLE-2
- **SLE-3:** https://github.com/kudalkargouri-crypto/SLE3

## 11. References

- SLE-2: Profiling Report — BFS vs DFS.
- SLE-3: Architectural Design using the Full C4 Model.
- SLE-4: Architecture Decision Record.
- Project source code and documentation maintained in GitHub.

## 12. Conclusion

The project demonstrates how BFS and DFS can be implemented and compared using empirical performance measurements. BFS recorded a lower average execution time than DFS in the reported experiment, while both algorithms found the goal after expanding 800 nodes.

The C4 architecture and ADR document the system structure and explain why a modular design was selected. Separating graph management, search algorithms, performance measurement, and output makes the system easier to understand, test, and maintain.

Overall, the project provides practical experience in AI search algorithms, performance evaluation, software architecture, and architectural decision-making.
