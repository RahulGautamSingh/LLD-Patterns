## Why

When one object changes state, multiple other objects need to know about it, but you do not want them tightly coupled.

## Example

```python
class EventManager:
    def __init__(self):
        self.listeners = {}

    def subscribe(self, event_type, listener):
        self.listeners.setdefault(event_type, []).append(listener)

    def notify(self, event_type, data):
        for listener in self.listeners.get(event_type, []):
            listener.update(data)

# Usage: Stock price changes notify Dashboard, AlertService, Logger
```

## Usage

1. Stock Ticker (price updates)
2. Notification System
3. Auction System (bid updates)
4. Social Media Feed (new post alerts)
5. Library System (book available alerts).
