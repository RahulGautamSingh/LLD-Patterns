## Why

Ensure only a single instance of a class exists globlly

> Singleton is the most famous pattern but also the most overused. It introduces global state, makes testing harder, and hides dependencies.
> Use it only for things like configuration managers, connection pools, or loggers where a single instance genuinely makes sense.

## Example

```python
class DatabaseConnection:
    _instance = None

    @classmethod
    def get_instance(cls):
        if cls._instance is None:
            cls._instance = cls()
        return cls._instance
```

## Usage

1. Database connection pool
2. Configuration manager
3. Logger instance
