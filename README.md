# python-redis-cache
Simple redis cache for Python functions

### Requirements
- Redis 5
- Python 3.6

## How to install
```
pip install python-redis-cache
```

## How to use
```python
from redis import StrictRedis
from redis_cache import RedisCache

redis_client = StrictRedis(host="redis", decode_responses=True)
cache = RedisCache(redis_client=client)


@cache.cache()
def my_func(arg1, arg2):
    # Some expensive operation
    return 5

```

## Limitations
Arguments and return types must be JSON serializable by default. You can override the serializer, but be careful with using Pickle. Make sure you understand the security risks.

