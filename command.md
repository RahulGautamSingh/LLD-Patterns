## Why

Encapsulates a request as an object, allowing you to parameterize, queue, log, or undo operations.

## Example

```python
class Command:
    def execute(self): pass
    def undo(self): pass

class BoldCommand(Command):
    def __init__(self, editor):
        self.editor = editor

    def execute(self):
        self.editor.apply_bold()

    def undo(self):
        self.editor.remove_bold()

# Command history enables Ctrl+Z
history = []
cmd = BoldCommand(editor)
cmd.execute()
history.append(cmd)
# Undo: history.pop().undo()
```

## Usage

1. Text Editor (undo/redo)
2. Remote Control system
3. Task queue
4. Transaction management
