# Hybrid Search with DocArray and Weaviate

This repo contains a notebook guide to using DocArray with Weaviate as storage backend to perform three different approaches to retrieval:

  1. Pure text search (symbolic search with BM25)
  2. Vector search and
  3. Hybrid search (combining symbolic and vector approaches)
  
Before starting on the notebook, make sure you have a docker instance with Weaviate running locally, or set credentials for connecting to a remote instance (requiring slight modifications to the notebook itself). To run Weaviate locally, first download the latest `docker-compose.yml` and then run it:

```
curl -o docker-compose.yml "https://configuration.weaviate.io/v2/docker-compose/docker-compose.yml?modules=standalone&runtime=docker-compose&weaviate_version=v1.19.2"

docker-compose up -d
```

This will start the Weaviate cluster locally. Note that we have specified the version v1.19.2 above, which should be updated with the latest release from Weaviate (check the [latest version here](https://github.com/weaviate/weaviate/releases)).

Next, you will need to create a virtual environment with all requirements installed:

```
python3 -m venv hybrid-venv
source hybrid-venv/bin/activate
pip install -r requirements.txt
```

It's also a good idea to register this new environment as an ipykernel:

```
python -m ipykernel install --user --name=hybrid-venv
```

You can now select this kernel on the top right corner of your notebook and be certain that you have all dependencies ready and installed!