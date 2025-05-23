# NodeLLM
NodeLLM is a class that extends the Node class in Godot. It is designed to provide a simple interface for working with large language models (LLMs) in a Godot project. It utilizes the signal mechanism of Godot to allow for asynchronous communication with the LLM, making it suitable for game development without blocking the main thread.

```admonish summary
[toc]
```

## Properties
- `api_type`: The type of API to be used for the LLM. It can be either "OpenAICompitable" or "Ollam".
- `base_url`: The base URL for the LLM API. It is used to make requests to the LLM.
- `model`: The model to be used for the LLM. It is a string that specifies the model name.
- `api_key`: The API key for authentication with the LLM API. It is a string that is required for accessing the LLM.
- `temperature`: The temperature parameter for the LLM. It is a float value that controls the randomness of the output. A higher value results in more random output, while a lower value results in more deterministic output.
- `max_tokens`: The maximum number of tokens to be generated by the LLM. It is an integer value that limits the length of the output.

## Methods
- `query(system_prompt: String, user_prompt: String)`

This method is used to send a query to the LLM and receive a response. It takes a string as system prompt and a string as user prompt. The method will emit the `response` signal with the response from the LLM in the future. A response processor function should be connected to this signal to handle the response.

```admonish example
Example of using NodeLLM in GDScript
```

Add a NodeLLM node to your scene and set its properties in the scene root node's `_ready` function. Connect the `response` signal to a function that processes the response from the LLM.

```gdscript

@onready var llm = $NodeLLM

_ready():
    
    # Set the properties for the LLM with scripts or in the editor's inspector
    llm.api_type = "Ollam"
    llm.base_url = "http://localhost:11434"
    llm.model = "qwen2.5:1.5b"
    llm.api_key = "your_api_key_here"
    llm.temperature = 0.7
    llm.max_tokens = 2048
    
    # Connect the response signal to a response processor function
    llm.response.connect(_on_response)
    
    # Send a query to the LLM
    var system_prompt = "You are a helpful assistant."
    var user_prompt = "What is the capital of France?"
    llm.query(system_prompt, user_prompt)

_on_response(response: String) -> void:
    # Process the response from the LLM
    print("Response from LLM: ", response)

```