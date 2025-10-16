# Foundation: Introduction to LangGraph

---

## Module 0:

[arnavv06-langgraph-mat496/module-0 at main · MAT496-Monsoon2025-SNU/arnavv06-langgraph-mat496](https://github.com/MAT496-Monsoon2025-SNU/arnavv06-langgraph-mat496/tree/main/module-0)

There wasn't much to learn as everything had been covered before.

Set API keys and loaded the .env file. Also instantiated two models and used **.invoke()** and **.stream()** to pass HumanMessage as a string and get AIMessage as output.

*Changes made:*

Changed and added new prompts.

---

## Module 1:

[arnavv06-langgraph-mat496/module-1 at main · MAT496-Monsoon2025-SNU/arnavv06-langgraph-mat496](https://github.com/MAT496-Monsoon2025-SNU/arnavv06-langgraph-mat496/tree/main/module-1)

### Video 1: Motivation

Learned that **Chains** are fixed control flows set by the developer, and an A**gent** controls the flow defined by an LLM. As more control is given to the agent, the application's reliabilty decreases. **LangGraph** is used to increase this reliability.

*Changes made:*

There wasn't any code so no changes had to be made.

### Video 2: Simple Graph

[arnavv06-langgraph-mat496/module-1/simple-graph.ipynb at main · MAT496-Monsoon2025-SNU/arnavv06-langgraph-mat496](https://github.com/MAT496-Monsoon2025-SNU/arnavv06-langgraph-mat496/blob/main/module-1/simple-graph.ipynb)

Learned a very simple **graph** structure consisting of **nodes** and simple/conditional **branches**. Created one function to define "node" and one for "branch"

Learned how to create a graph using  **StateGraph()** which has a simple edge from Start to Node1, and **conditional edges** further ahead to decided which node to go to based on the parameters passed.

*Changes Made:*

* Created and added a couple of more **nodes** to the graph.
* Created more **conditional branches** and connected them in graph.
* Changed the branch function to decide which drink I like.

### Video 3: Langsmith Studio
