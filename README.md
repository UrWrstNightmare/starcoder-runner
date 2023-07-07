# Local StarCoder Inference Server

## Installation & venv
1. Install `pyenv` (SEE https://realpython.com/intro-to-pyenv/)
2. Setup `pyenv` in `$SHELL`
3. `pyenv install 3.11.4`
4. `pyenv virtualenv 3.11.4 starcoder_py311`
5. `pyenv virtualenvs` to list
6. `pyenv activate starcoder_py311`
7. `pip install -r requirements.txt`
8. Log in to huggingFace via `huggingface-cli login` OR by manually providing a login token

## Running
`python main.py --port 8000 --host 0.0.0.0 --pretrained bigcode/starcoderplus`


**Base code from [LucienShui/huggingface-vscode-endpoint-server](https://github.com/LucienShui/huggingface-vscode-endpoint-server/blob/main/requirements.txt)**

---

# Hugging Face VSCode Endpoint Server

starcoder server for [huggingface-vscdoe](https://github.com/huggingface/huggingface-vscode) custom endpoint.

**Can't handle distributed inference very well yet.**

## Usage

```shell
pip install -r requirements.txt
python main.py
```

Fill `http://localhost:8000/api/generate/` into `Hugging Face Code > Model ID or Endpoint` in VSCode.

## API

```shell
curl -X POST http://localhost:8000/api/generate/ -d '{"inputs": "", "parameters": {"max_new_tokens": 64}}'
# response = {"generated_text": ""}
```
