## Why

Making two incompatible interfaces work together. The classic "square peg in a round hole" problem.

## Example

```python
class OldPaymentGateway:
    def make_payment(self, amount_in_cents):
        print(f"Paid {amount_in_cents} cents")

class ModernPaymentAdapter:
    def __init__(self, old_gateway):
        self.old = old_gateway

    def pay(self, amount_in_dollars):
        self.old.make_payment(int(amount_in_dollars * 100))
```

## Usage

1. Payment gateway integrations (old API to new API)
2. Third party service wrappers
3. Legacy system migration
