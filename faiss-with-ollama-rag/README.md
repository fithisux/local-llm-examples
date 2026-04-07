# Local LLM with FAISS and Ollama.

Succesful experiments on using local llm to query a piece of literature with FAISS and ollama.
We will use **gemma:2b** for natural language answers and *nomic-ai/nomic-embed-text-v1* for relevance retrieval.

# Model load

Install from [requirements.txt](./requirements.txt)

You also need to load **gemma:2b** in ollama, whhich is assumed to be installed on you PC or your Podman install.

```
ollama pull gemma:2b

```

# Excution

Download the Trial by Sorcery file from here https://manybooks.net/titles/trial-by-sorcery and save it as [Trial-by-Sorcery.pdf](./Trial-by-Sorcery.pdf).

Given you have jupyter configured properly as in the top level README

```
python -m pip install -r requirements.txt

```

Now you can use venv314 kernel to run the [ollama-gemma.ipynb](ollama-gemma.ipynb).