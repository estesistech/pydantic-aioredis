Extras
======
pydantic-aioredis works well with other python modules in the pydantic ecosystem. There are some extras offered to make
those integrations tighter

FastAPI
-------
The FastAPI extra adds a new base model called FastAPIModel. It has a single additional classmethod, select_or_404.

.. automodule:: pydantic_aioredis.ext.FastAPI
    ::member::
