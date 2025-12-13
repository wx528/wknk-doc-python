# alembic

## Install
```bash
pip install alembic
```

## Quick usage

```bash
alembic init

alembic revision -m "update something"
alembic revision --autogenerate -m "something"
alembic history
alembic upgrade head
alembic show 

```

## Advanced usage

```
alembic revision --autogenerate -m "something"
alembic upgrade head
```
if you want autogenerate again before update head
use alembic history to see what is the id of last revision
and delete the change file  in \alembic\versions\
```
alembic history 
```