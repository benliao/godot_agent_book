# AgentActionManager

This class is responsible for managing the actions of the agent. It handles the execution of actions, the management of action queues, and the interaction with the agent's state and memory.

```admonish summary
[toc]
```

## Properties
- `candidate_actions`: A list of actions that are candidates for execution. These actions are generated based on the agent's memory and the current state of the game.
- `action_queue`: A queue that holds the actions to be executed by the agent. It is a list of AgentAction instances.
- `current_actions`: The actions that are currently being executed by the agent. In some situations, multiple actions can be executed simultaneously.

## Methods
- `add_action`: Adds a new action to the action queue. It takes an AgentAction instance as a parameter.
- `remove_action`: Removes an action from the action queue. It takes an AgentAction instance as a parameter.
