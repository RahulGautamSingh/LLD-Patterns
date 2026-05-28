## Why

Passes a request through a chain of handlers, where each handler either processes it or forwards it to the next one.

## Example

```python
class Handler:
    def __init__(self, next_handler=None):
        self.next = next_handler

    def handle(self, request):
        if self.next:
            self.next.handle(request)

class AuthHandler(Handler):
    def handle(self, request):
        if not request.get("token"):
            return "Unauthorized"
        super().handle(request)

class RateLimitHandler(Handler):
    def handle(self, request):
        if request.get("rate") > 100:
            return "Rate limited"
        super().handle(request)

# Chain: Auth → RateLimit → BusinessLogic
chain = AuthHandler(RateLimitHandler(BusinessLogicHandler()))
```

## Usage

1. Middleware pipelines (auth → rate limit → logging → handler)
2. Logger (different log levels)
3. Approval workflows (manager → director → VP)
4. Exception handling chains
