## Why

Defines the skeleton of an algorithm in a base class, letting subclasses override specific steps without changing the overall structure.

## Example

```python
class DataProcessor:
    def process(self):       # Template method
        data = self.read()
        cleaned = self.clean(data)
        result = self.analyze(cleaned)
        self.save(result)

    def read(self): pass     # Subclasses override these
    def clean(self, data): pass
    def analyze(self, data): pass
    def save(self, result): pass

class CSVProcessor(DataProcessor):
    def read(self): return "csv data"
    def clean(self, data): return data.strip()
    # ... other steps
```


## Usage

1. Data pipeline processing
2. Game loop (init → update → render)
3. Report generation (fetch → format → export)
