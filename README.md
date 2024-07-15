# Learning privateGPT

Just one of the things I'm learning. https://github.com/hchiam/learning

https://github.com/hchiam/learning-ollama

## July 2024 notes:

https://github.com/zylon-ai/private-gpt (was https://github.com/imartinez/privateGPT)

https://docs.privategpt.dev/installation/getting-started/installation

For mac:

```sh
git clone https://github.com/zylon-ai/private-gpt
cd private-gpt
# install python 3.11, then continue with:
pyenv install 3.11
pyenv local 3.11
brew install pipx
pipx install poetry
brew install make
set PGPT_PROFILES=ollama
make run
# install ollama (run the desktop installer to install the CLI command ollama)
ollama pull mistral
ollama pull nomic-embed-text
ollama serve # to run server (I had to manually re-close the ollama desktop app)
# and in a separate terminal:
poetry install --extras "ui llms-ollama embeddings-ollama vector-stores-qdrant"
# make sure ollama running locally before run this:
PGPT_PROFILES=ollama make run
# http://localhost:8001
# it took about 2 minutes to respond to short questions about a local text file on my desktop, of course offline
# and close both terminals when you're done
# if you want to reclaim space used by the model and embeddings, use ollama CLI:
ollama list
# then ollama rm <name-of-thing-to-remove>
```

## March 2024 notes:

https://github.com/imartinez/privateGPT

https://docs.privategpt.dev/overview/welcome/quickstart

https://docs.privategpt.dev/api-reference/overview/api-reference-overview

You might have to `brew install python@3.11` because privateGPT currently requires `python = ">=3.11,<3.12"`

```sh
git clone https://github.com/imartinez/privateGPT

cd privateGPT

python3.11 -m venv .venv
# or with my alias: py -m venv .venv
# given this .bash_profile alias: alias py='python3.11'

source .venv/bin/activate

pip install --upgrade pip poetry

poetry install --with ui,local
# i had to run this instead: poetry install

./scripts/setup

# Launch the privateGPT API server **and** the gradio UI
poetry run python3.11 -m private_gpt
# this also failed for me

# In another terminal, create a new browser window on your private GPT!
open http://127.0.0.1:8001/
```
