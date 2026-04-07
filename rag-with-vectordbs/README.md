# Example of simple vector DB search

## Set up

Create a folder called compass documents where you add the compass documents.
Now create a folder named `volumes` and subfolders `backends, images, models`. This will hold LocalAI models.
Also you need to create a `typesense_data`. You need this for correct permissions.

Now you can start the LocalAI+Typesense combo with (I use podman, you can use docker)

```
podman compose up
```

and shut it down with, when you do not need it with

```
podman compose down -v
```

## Execution

Given you have jupyter configured properly as in the top level README

```
python -m pip install -r requirements.txt

```

Now you can use venv314 kernel to run [the weaviate notebook](./markdown_embed_weaviate.ipynb)
or the [markdown_embed_typesense.ipynb](markdown_embed_typesense.ipynb) notebooks.


### LLM configuration for LocalAI

You can avoid OpenAI by using LocalAI with the "LFM2.5-1.2B-Instruct-GGUF"
model.

```
docker compose -f typesense-docker-compose.yml up 
```

Then navigate to the [local home page](http://localhost:8081/) and import the model mentioned previously from this [url](https://huggingface.co/unsloth/LFM2.5-1.2B-Instruct-GGUF)

when you do not want the container anymore

```
docker compose -f typesense-docker-compose down
```


### LLM configuration for Ollama

You can install **nomic-embed-text** embedding model and the **"LFM2.5-1.2B-Instruct**  LLM for ollama by first startting the weaviate compose file.

```
docker compose -f weaviate-docker-compose.yml up 
```

Use `docker ps` to find ollama container id, say **ollamaid**.
Connect then to this containers, so as to pull the model

```
docker exec -it ollamaid /bin/bash
ollama pull nomic-embed-text
ollama pull sam860/lfm2.5:1.2b
```

When you do not want the container anymore

```
docker compose -f weaviate-docker-compose down
```