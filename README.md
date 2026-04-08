# Local LLM examples

## What is this about

There are two classes of examples.

1. Local LLM with FAISS and OLLAMA [here](faiss-with-ollama-rag)
2. Local LLM with Weaviate or Typesense [here](rag-with-vectordbs)

It is suggested to do your learning process as follows

a. FAISS lesson
b. Typesense lesson
c. Weaviate lesson


## How to use it

See individual folders for more detailed instructions.

You need to create a virtual environment. I have tested with Python 3.14.3x64 on Windows 11.
The most convenient approach is to use venv

```
uv venv --python 3.14

```

and activate it with

```
.venv\Scripts\activate
python -m ensure pip

```

Given you have jupyter in system python

```
python -m pip install ipykernel
python -m ipykernel install --user --name venv314

```

Now you can use venv314 kernel to run your notebooks.

## Help

Open an issue or notify vasilis.anagnostopoulos@agileactors.com