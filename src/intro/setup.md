# Setup

Before we can demostrate our examples, we need to install some tools.

## Ollama

[Ollama][ollama] is a convenient LLM infer engine for PC deployment, especially for relatively small models. It is a great tool for local development and testing.

QWen 2.5 1.5b is a great model for our examples, as it is small enough to run on most PCs and has a good performance. You can install it with the following command in your terminal after installing Ollama.

```bash
ollama run qwen2.5:1.5b
```

## SurrealDB

[SurrealDB][surrealdb] is a powerful database that can be used for various purposes, including storing and retrieving data for our examples. It features a flexible schema and includes a mongodb-like document store, a vector store, a graph database, and a time-series store. It is a great choice for our examples, as it allows us to easily store and retrieve data in a variety of formats.

After installing SurrealDB, you can start it with the following command in your terminal:

```bash
surreal start --user root --pass root --bind 127.0.0.1:4747 rocksdb://db/agent.db
```

## Godot Engine

Godot Engine 4.4.1 is tested with this book. You can download it from the [Godot Engine website][godot].

## Godot Agent Extension
The Godot Agent extension is a plugin for Godot Engine that allows you to easily integrate LLM and related technologies into your Godot projects. You may create an LLM agent in your Godot project and use it to interact with your game world. The extension is designed to be easy to use and flexible, allowing you to customize it to fit your needs.

[godot]: https://godotengine.org/download
[surrealdb]: https://surrealdb.com/
[ollama]: https://ollama.com/