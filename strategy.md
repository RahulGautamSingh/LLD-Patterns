## Why?

Incase you have multiple algorithms for the same problem, but need to pick one depending on context.

## Example

```python
# Without Strategy (ugly switch)
def calculate_fare(ride_type, distance):
    if ride_type == "pool":
        return distance * 5
    elif ride_type == "go":
        return distance * 10
    elif ride_type == "premier":
        return distance * 20

# With Strategy (clean, extensible)
class FareStrategy:
    def calculate(self, distance): pass

class PoolFare(FareStrategy):
    def calculate(self, distance): return distance * 5

class PremierFare(FareStrategy):
    def calculate(self, distance): return distance * 20

class Ride:
    def __init__(self, strategy: FareStrategy):
        self.strategy = strategy

    def fare(self, distance):
        return self.strategy.calculate(distance)
```

### Real World Examples

1. Parking Lot (pricing strategies)
2. Chess (piece movement strategies)
3. Payment System (credit card vs UPI vs wallet)
4. Ride Sharing (fare calculation).
