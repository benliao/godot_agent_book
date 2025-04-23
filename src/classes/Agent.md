# Agent
Agent class is built on top of the NodeLLM class. It is used to create an agent that can interact with the environment and perform tasks. The agent can be configured with different parameters such as memory, action, and state. 

```admonish summary
[toc]
```

It makes use of a NodeLLM instance to perform language model queries. The agent can be used to create complex behaviors and interactions in a Godot game. It can also utilize various plugins to enhance its capabilities, making it a versatile tool for game development.

## Properties
- `llm`: An instance of the NodeLLM class. It is used to perform language model queries.
- `agent_memory`: An instance of the AgentMemory class. It is used to manage the agent's memory.

## Methods
- `query`: Sends a query to the LLM and receives a response. It takes a string as system prompt and a string as user prompt. The method will emit the `response` signal with the response from the LLM in the future. A response processor function should be connected to this signal to handle the response.
