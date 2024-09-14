# Key Concepts

### 1. Nodes

**Nodes are the key components of a agent**. By connecting nodes with different functionalities, you can execute a series of operations within the agent.

For core agent nodes, please refer to [Node Description](node/README.md).

***

### 2. Variables

**Variables are used to link the input and output of nodes within a agent**, enabling complex processing logic throughout the process.

* A agent needs to define execution start variables, such as defining an input variable `sys.query` for a chatbot.
* Nodes generally need to define input variables, such as defining the input variable for a question classifier as `sys.query`.
* When referencing variables, only upstream node variables in the process can be referenced.
* To avoid variable name conflicts, node names must be unique.
* The output variables of nodes are generally system-fixed variables and cannot be edited.

***

<!-- ### 3. Chatflow and Agent

**Application Scenarios**

* **Chatflow**: Designed for conversational scenarios, including customer service, semantic search, and other conversational applications that require multi-step logic in response construction.
* **Agent**: Geared towards automation and batch processing scenarios, suitable for high-quality translation, data analysis, content generation, email automation, and more. -->

<!-- **Usage Entry Points**

<figure><img src="/en/.gitbook/assets/guides/workflow/key-concepts/output.png" alt=""><figcaption><p>Chatflow Entry</p></figcaption></figure>

<figure><img src="/en/.gitbook/assets/guides/workflow/key-concepts/output (4).png" alt=""><figcaption><p>Agent Entry</p></figcaption></figure>

**Differences in Available Nodes**

1. The End node is an ending node for Agent and can only be selected at the end of the process.
2. The Answer node is specific to Chatflow, used for streaming text output, and can output at intermediate steps in the process.
3. Chatflow has built-in chat memory (Memory) for storing and passing multi-turn conversation history, which can be enabled in nodes like LLM and question classifiers. Agent does not have Memory-related configurations and cannot enable them.
4. Built-in variables for Chatflow's start node include: `sys.query`, `sys.files`, `sys.conversation_id`, `sys.user_id`. Built-in variables for Agent's start node include: `sys.files`, `sys_id`. -->