# poetry usage


## Basic 
Install poetry
```
# if not have pipx ,install it in front
# pip install pipx 
pipx install poetry
```

See help 
```
poetry
```


```
poetry init -n
```


Installing dependencies in a new cloned project
```bash
poetry install
```


Show Python versions available in the environment.
```
poetry python list
```



Export requirments
```
poetry self add poetry-plugin-export
poetry export --without-hashes > requirements.txt
```