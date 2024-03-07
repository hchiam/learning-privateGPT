# Learning privateGPT

Just one of the things I'm learning. https://github.com/hchiam/learning

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
