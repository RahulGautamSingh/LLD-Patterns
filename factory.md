## Why

Object creation logic is complex or depends on runtime input, and you want to centralize it instead of scattering new calls everywhere.

## Example

```python
class VehicleFactory:
    @staticmethod
    def create(vehicle_type: str):
        if vehicle_type == "car":
            return Car()
        elif vehicle_type == "truck":
            return Truck()
        elif vehicle_type == "bike":
            return Bike()
        raise ValueError(f"Unknown type: {vehicle_type}")

# Caller does not need to know which class to instantiate
vehicle = VehicleFactory.create("car")
```

## Usage

1. Parking Lot (vehicle types)
2. Logger (file logger vs console logger vs DB logger)
3. Document Editor (creating different document types)
4. Game (enemy/character creation).
