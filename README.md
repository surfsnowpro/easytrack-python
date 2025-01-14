# Easytrack - Python
## Project Organization
| Package | Description |
| --- | --- |
| `app/api/endpoints` | Files containing endpoint definitions and entry points. |
| `app/api/schemas` | Definitions for schemas to be returned from endpoints. Schema classes should inherit from `pydantic`s `BaseModel` class. |
| `app/db/models` | Database models for use with the `SQLAlchemy` ORM.  These should inherit from a common `declarative_base` |
While models and schemas may end up resembling a 1:1 relationship, this doesn't have
to be the case.

### Discussion
* Renaming `endpoints` to `services`
* Flatten `api` package and merge `endpoints` and `schemas` to `app` package
* Naming convention for metadata generated by `SQLAlchemy`: 
```python
convention = {
    "ix": "ix_%(column_0_label)s",
    "uq": "uq_%(table_name)s_%(column_0_name)s",
    "ck": "ck_%(table_name)s_%(constraint_name)s",
    "fk": "fk_%(table_name)s_%(column_0_name)s_%(referred_table_name)s",
    "pk": "pk_%(table_name)s",
}
```