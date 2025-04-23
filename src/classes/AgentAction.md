# AgentAction
AgentAction is a class that represents an action taken by an agent. It is used to define the action that the agent will take in the game. The action can be a simple action or a complex action that involves multiple steps. The class is designed to be flexible and extensible, allowing developers to create custom actions for their agents. An agent action should provide a tick method that will be called every frame to update the action's state. The action can also be paused and resumed, allowing for more complex behaviors. Additionally, the class should implement methods for starting, stopping, and resetting the action, ensuring that agents can manage their actions effectively.

```admonish summary
[toc] 
```

## Properties
- `action_name`: The name of the action. It is a string that identifies the action.
- `action_type`: The type of action. It is a string that specifies the type of action, such as "move", "attack", etc.
- `action_data`: The data associated with the action. It is a dictionary that contains additional information about the action, such as target position, target entity, etc.
- `action_state`: The state of the action. It is a string that indicates the current state of the action, such as "running", "paused", "stopped", "success", or "failed", etc.
- `action_priority`: The priority of the action. It is an integer that determines the order in which actions are executed. Higher values indicate higher priority.


## Methods
- `start`: Starts the action. This method should be called to initiate the action. It may perform any necessary setup or initialization for the action.
- `stop`: Stops the action. This method should be called to terminate the action. It may perform any necessary cleanup or finalization for the action.
- `pause`: Pauses the action. This method should be called to temporarily halt the action. It may save the current state of the action so that it can be resumed later.
- `resume`: Resumes the action. This method should be called to continue the action after it has been paused. It may restore the state of the action to what it was before it was paused.
- `reset`: Resets the action. This method should be called to reset the action to its initial state. It may clear any data or state associated with the action.
- `tick`: Updates the action's state. This method should be called every frame to update the action's state. It may perform any necessary calculations or updates based on the current state of the action and the game environment. It also returns an enum value indicating the status of the action, such as "running", "paused", "stopped", "success", or "failed".
