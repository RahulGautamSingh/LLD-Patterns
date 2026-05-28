## Why

Constructing complex objects step by step, especially when the constructor would need too many parameters.

## Example

```python
class QueryBuilder:
    def __init__(self):
        self._table = None
        self._conditions = []
        self._limit = None

    def table(self, name):
        self._table = name
        return self

    def where(self, condition):
        self._conditions.append(condition)
        return self

    def limit(self, n):
        self._limit = n
        return self

    def build(self):
        query = f"SELECT * FROM {self._table}"
        if self._conditions:
            query += " WHERE " + " AND ".join(self._conditions)
        if self._limit:
            query += f" LIMIT {self._limit}"
        return query

# Clean, readable construction
query = QueryBuilder().table("users").where("age > 25").limit(10).build()
```

## Usage

1. Query builders
2. Meal/Order builders (restaurant system)
3. Document creation
4. Complex configuration objects
