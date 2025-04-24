
# AgentMemory
AgentMemory is a class that manages the memory of an agent. It stores the agent's memory and provides methods to add, retrieve, and clear memory. The memory is stored in SurrealDB through the AgentDb class.

```admonish summary
[toc]
```

## Properties
- `agent_id`: The ID of the agent.
- `agent_db`: An instance reference to the AgentDb class.

## Methods
- `add_memory`: Adds a new memory to the agent's memory.
- `get_memory`: Retrieves the agent's memory with a sql condition.
- `clear_memory`: Clears the agent's memory.

### add_memory
```gdscript
func add_memory(memory: Dictionary) -> void
```
### parameters
#### memory
A dictionary containing the memory to be added. The dictionary should contain the following keys:
  - `subjet`: Who or What the memory is about.
  - `verb`: What happened in the memory.
  - `object`: The object of the memory.
  - `location`: The location of the memory.
  - `data`: The data of the memory.

```admonish example
Agent read a book
```

```gdscript
var memory = {
    "subjet": "Agent",
    "verb": "read",
    "object": "book",
    "location": "library",
    "data": "The book is about AI.",
}
agent_memory.add_memory(memory)
```

```admonish example
Agent talked to a person
```

```gdscript
var memory = {
    "subjet": "Agent",
    "verb": "talked to",
    "object": "person",
    "location": "park",
    "data": "Let's meet at the park tomorrow.",
}
agent_memory.add_memory(memory)
```

```admonish example
Sommeone said something
```

```gdscript
var memory = {
    "subjet": "Someone",
    "verb": "said",
    "object": "something",
    "location": "home",
    "data": "I love this place.",
}
agent_memory.add_memory(memory)
```

```admonish example
Someone cooked a meal
```

```gdscript
var memory = {
    "subjet": "Someone",
    "verb": "cooked",
    "object": "a meal",
    "location": "home",
    "data": "The meal is delicious.",
}
agent_memory.add_memory(memory)
```

```admonish example
It's raining
```

```gdscript
var memory = {
    "subjet": "Weather",
    "verb": "is raining",
    "object": "",
    "location": "town",
    "data": "It's raining heavily outside.",
}
agent_memory.add_memory(memory)
```

### get_memory
```gdscript
func get_memory(sql_condition: String)
signal result(result: Array<Dictionary>)
```
#### parameters
- `sql_condition`: A SQL condition to filter the memory. The condition should be in the format of a SQL WHERE clause.

```admonish example
All memories about the "Agent read a book"
```

```gdscript
# connect the result signal to a result processor
agent_memory.result.connect(_on_result)

# define the sql condition, the filed name should be followed with 'fields' as prefix lie below
# fields.subjet = 'Agent' AND fields.verb = 'read'

var sql_condition = "fields.subjet = 'Agent' AND fields.verb = 'read'"
agent_memory.get_memory(sql_condition)

# the result will be processed in the _on_result function
# when the result is ready, the result signal will be emitted and the _on_result function will be called

func _on_result(result: Array<Dictionary) -> void:
    for memory in result:
        print(memory)
```

### clear_memory
clears the agent's memory.

```gdscript
func clear_memory() -> void
```