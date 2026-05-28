## Why

An object's behavior changes based on its internal state, and you want to avoid massive if/else chains checking the current state.

> Anytime you see state transitions: "pending → confirmed → shipped → delivered" or "idle → dispensing → out of stock."

## Example

```python
class VendingMachineState:
    def insert_coin(self, machine): pass
    def select_item(self, machine): pass
    def dispense(self, machine): pass

class IdleState(VendingMachineState):
    def insert_coin(self, machine):
        print("Coin accepted")
        machine.set_state(HasCoinState())

class HasCoinState(VendingMachineState):
    def select_item(self, machine):
        print("Item selected, dispensing...")
        machine.set_state(DispensingState())
```

## Usage

1. Vending Machine
2. Elevator System
3. Order Management (order lifecycle)
4. ATM
5. Traffic Light Controller
6. Document Workflow (draft → review → published)
