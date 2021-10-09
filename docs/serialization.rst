Serialization
=============

Data in Redis
-------------
pydantic-aioredis uses Redis Hashes to store data. The ```_primary_key_field``` of each Model is used as the key of the hash.

Because Redis only supports string values as the fields of a hash, data types have to be serialized.

Simple data types
-----------------
Simple python datatypes that can be represented as a string and natively converted by pydantic are converted to strings and stored. Examples
are ints, floats, strs, bools, and Nonetypes.

Complex data types
------------------
Complex data types are dumped to json with json.dumps().

Custom serialization is possible by overriding the serialize_partially and deserialize_partially methods in `AbstractModel <https://github.com/andrewthetechie/pydantic-aioredis/blob/main/pydantic_aioredis/abstract.py#L32>`_.

It is also possilbe to override json_default in AbstractModel. json_default is a callable used to convert any objects of a type json.dump cannot natively dump to string.

Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
