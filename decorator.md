## Why

Adding behavior to an object dynamically without modifying its class. Like wrapping a gift: the gift stays the same, but each wrapper adds something.

## Example

```python
class Coffee:
    def cost(self): return 5

class MilkDecorator:
    def __init__(self, coffee):
        self.coffee = coffee
    def cost(self): return self.coffee.cost() + 2

class SugarDecorator:
    def __init__(self, coffee):
        self.coffee = coffee
    def cost(self): return self.coffee.cost() + 1

# Stack decorators: Coffee + Milk + Sugar = 5 + 2 + 1 = 8
drink = SugarDecorator(MilkDecorator(Coffee()))
```

## Usage

1. Pizza/Coffee ordering (toppings)
2. Stream processing (buffered + encrypted + compressed stream)
3. Notification channels (email + SMS + push)
