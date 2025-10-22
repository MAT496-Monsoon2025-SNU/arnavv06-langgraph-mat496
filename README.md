# Foundation: Introduction to LangGraph

---

## Module 0:

[arnavv06-langgraph-mat496/notebooks/module-0 at main · MAT496-Monsoon2025-SNU/arnavv06-langgraph-mat496](https://github.com/MAT496-Monsoon2025-SNU/arnavv06-langgraph-mat496/tree/main/notebooks/module-0)

There wasn't much to learn as everything had been covered before.

Set API keys and loaded the .env file. Also instantiated two models and used **.invoke()** and **.stream()** to pass HumanMessage as a string and get AIMessage as output.

*Changes made:*

Changed and added new prompts.

---

## Module 1:

[arnavv06-langgraph-mat496/notebooks/module-1 at main · MAT496-Monsoon2025-SNU/arnavv06-langgraph-mat496](https://github.com/MAT496-Monsoon2025-SNU/arnavv06-langgraph-mat496/tree/main/notebooks/module-1)

### Video 1: Motivation

Learned that **Chains** are fixed control flows set by the developer, and an A**gent** controls the flow defined by an LLM. As more control is given to the agent, the application's reliabilty decreases. **LangGraph** is used to increase this reliability.

*Changes made:*

There wasn't any code so no changes had to be made.

### Video 2: Simple Graph

[arnavv06-langgraph-mat496/notebooks/module-1/simple-graph.ipynb at main · MAT496-Monsoon2025-SNU/arnavv06-langgraph-mat496](https://github.com/MAT496-Monsoon2025-SNU/arnavv06-langgraph-mat496/blob/main/notebooks/module-1/simple-graph.ipynb)

Learned a very simple **graph** structure consisting of **nodes** and simple/conditional **branches**. Created one function to define "node" and one for "branch"

Learned how to create a graph using  **StateGraph()** which has a simple edge from Start to Node1, and **conditional edges** further ahead to decided which node to go to based on the parameters passed.

*Changes Made:*

* Created and added a couple of more **nodes** to the graph.
* Created more **conditional branches** and connected them in graph.
* Changed the branch function to decide which drink I like.

### Video 3: Langsmith Studio

Learned to visualise graphs as flowcharts using **Langsmith Studio**. Previosly it was being shown in jupyter notebook.

*Changes made:*

Edited **simple.py** file according to the graph I constructed in previous notebook.

![1760608678635](image/README/1760608678635.png)

### Video 4: Chain

[arnavv06-langgraph-mat496/notebooks/module-1/chain.ipynb at main · MAT496-Monsoon2025-SNU/arnavv06-langgraph-mat496](https://github.com/MAT496-Monsoon2025-SNU/arnavv06-langgraph-mat496/blob/main/notebooks/module-1/chain.ipynb)

Initially learned how to use messages as inputs to chat models, bind tools to them and get tool calls output.

I also learned how to implemented the same thing as a **chain** using a graph. A list of messages and a tool is first created, which are then put together in a graph as nodes and connected through edges. This comprises a chain.

*Changes made*:

* Changed messages to ask about some exercises.
* Created my own translational tool and replaced it in the code with the given one.

### Video 5: Router

[arnavv06-langgraph-mat496/notebooks/module-1/router.ipynb at main · MAT496-Monsoon2025-SNU/arnavv06-langgraph-mat496](https://github.com/MAT496-Monsoon2025-SNU/arnavv06-langgraph-mat496/blob/main/notebooks/module-1/router.ipynb)

Learnt how to make an LLM decide whether to invoke a **tools call** or not by interpreting the input. This works kind of like a **router**. A tool call is generated only if a question requiring that is asked, otherwise the LLM reponds by itself. Verified the same on Langsmith Studio.

*Changes made:*

* Edited code to include the **translational tool** created previosly.
* Edited **router.py** file to inlcude the translational tool
* Gave different inputs in **Langsmith Studio**

![1760614891545](image/README/1760614891545.png)

![1760614995919](image/README/1760614995919.png)

### Video 6: Agent

[arnavv06-langgraph-mat496/notebooks/module-1/agent.ipynb at main · MAT496-Monsoon2025-SNU/arnavv06-langgraph-mat496](https://github.com/MAT496-Monsoon2025-SNU/arnavv06-langgraph-mat496/blob/main/notebooks/module-1/agent.ipynb)

Created an **Agent** that can solve mathematical expressions. Previously the 'router node' either ended the program or gave a tools call, but now the tools call is given back to the router node(assistant) which might go back to the tools call and this process can go on in a loop until the model produces a fit answer. This is the intuition behind **React** architecture.

*Changes Made*:

* Added more mathematical functions to **convert_to_binary()** , **calculate_twos_complement()** , **add_twos_complement_binaries()**, **convert_from_twos_complement()**.
* Changed the **input** to include the added mathematical functions.

![1760617695613](image/README/1760617695613.png)

### Video 7: Agent with Memory

[arnavv06-langgraph-mat496/notebooks/module-1/agent-memory.ipynb at main · MAT496-Monsoon2025-SNU/arnavv06-langgraph-mat496](https://github.com/MAT496-Monsoon2025-SNU/arnavv06-langgraph-mat496/blob/main/notebooks/module-1/agent-memory.ipynb)

Learned how to add **Memory** to an Agent. It is done using **MemorySaver()** which can be used to set a **checkpoint**. The checkpoint preserves the state of the graph at a particular stage. A collection of such checkpoints is called thread. Using this, we can save the output from a previous call and use it as input for the next call.

In Langsmith Studio, this happens by default using a persistence layer which provides memory to agent.

*Changes Made:*

* Added all the tools i had made previously and ran the agent with **memory** on those tools.
* Edited the **agent.py** file to include the newly added tools.

![1760619459539](image/README/1760619459539.png)

---

## Module 2: State and Memory

[arnavv06-langgraph-mat496/notebooks/module-2 at main · MAT496-Monsoon2025-SNU/arnavv06-langgraph-mat496](https://github.com/MAT496-Monsoon2025-SNU/arnavv06-langgraph-mat496/tree/main/notebooks/module-2)

### Video 1: State Schema

[arnavv06-langgraph-mat496/notebooks/module-2/state-schema.ipynb at main · MAT496-Monsoon2025-SNU/arnavv06-langgraph-mat496](https://github.com/MAT496-Monsoon2025-SNU/arnavv06-langgraph-mat496/blob/main/notebooks/module-2/state-schema.ipynb)

Learned that the **schema**(structure and datatype used by graph) we established earlier using **TypeDict**, the type hints are not enforced at runtime and an invalid value could be assigned without raising an error. This happens with **DataClass** too which is also used to define structured data. Using **Pydantic** prevents this from happening and provides data validation.

*Changes made:*

* Changed and added graph nodes and branches functions built using TypeDict
* Changed and added graph nodes and branches functions built using DataClass
* Changed and added graph nodes and branches functions built using Pydantic

### Video 2: State Reducers

[arnavv06-langgraph-mat496/notebooks/module-2/state-reducers.ipynb at main · MAT496-Monsoon2025-SNU/arnavv06-langgraph-mat496](https://github.com/MAT496-Monsoon2025-SNU/arnavv06-langgraph-mat496/blob/main/notebooks/module-2/state-reducers.ipynb)

I learned that when we invoke a graph by inputting a value of they, the defualt behaviour is to **overwrite** the value. This causes an error when two nodes are run in **parallel** as they try to overwrite within the same step of the graph. **Reducers** solve this problem by rather than overwriting the value returned by a node, the add it along with the initial value to a **list**.

Also learned about **MessageState()** and different reducers provided by it.

*Changes made:*

* Changed the key from foo to **candy**, and its value from int to type **string**
* Modified the graph to show the use of reducers using string
* Changed **messages** to ask some geographical questions.

### Video 3: Multiple Schemas

[arnavv06-langgraph-mat496/notebooks/module-2/multiple-schemas.ipynb at main · MAT496-Monsoon2025-SNU/arnavv06-langgraph-mat496](https://github.com/MAT496-Monsoon2025-SNU/arnavv06-langgraph-mat496/blob/main/notebooks/module-2/multiple-schemas.ipynb)

Learned about **Overall** and **Private** state. Private state lets different nodes of the graph to share information with each other without affecting the input or final output. Also learned how to define custom **Input/Output schema** because StateSchema() by default expects nodes to communicate using a single schema only. Using I/O schema, we can filter out on what is allowed in the input and output of the graph.

*Changes made*:

* Added a couple of more intermediate nodes in the graph
* Changed how data is manipulated in return statements.

### Video 4: Trim and Filter Messages

Learned how to use **RemoveMessage** and **MessagesState()** to **filter, trim** and control the chat history with model. This helps in reducing **token usage**.                                      Observed in **Langsmith UI** that the LLM only takes in input the last message appended to messages list.

*Changes Made:*

* Changed the conversation and message list from ocean mammals to secrets of the **cosmos**.

![1761170883123](image/README/1761170883123.png)


![1761170714216](image/README/1761170714216.png)


### Video 5:
