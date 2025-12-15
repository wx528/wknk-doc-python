# uv

## install 

```
pip install uv
# or 
pipx install uv

```
## create venv
```
uv venv
```

## install all the dependencies and delete ones that are not in the list
```
uv sync
```

## install and update dependencies
```
uv install
```

## generate requirements.txt
```
uv pip compile pyproject.toml -o requirements.txt
```