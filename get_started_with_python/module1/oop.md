# More About Object-Oriented Programming (OOP)

## Overview
Object-oriented programming (OOP) is a paradigm based around **objects** that combine data and the code to manipulate that data. **Classes** serve as blueprints for objects, bundling attributes (data) and methods (functions). While this course does not require creating your own classes, understanding the basics of OOP will be valuable as you progress in data analysis and programming.

---

## Key Concepts of OOP

### **1. Attributes and Methods**
- **Attributes**: Characteristics or values associated with an object. Accessed using dot notation without parentheses.
  - Example: `Spaceship.name`, `Spaceship.speed`
- **Methods**: Functions that belong to a class, performing actions or operations. Accessed using dot notation with parentheses.
  - Example: `Spaceship.warp(7)`  

| **Attribute** | **Method**       |
|---------------|------------------|
| `Spaceship.name` | `Spaceship.warp()` |
| `Spaceship.speed` | `Spaceship.tractor()` |

---

### **2. Defining Classes**
- Classes are defined using the `class` keyword. Attributes and methods are indented under the class definition.
- **Example:**
  ```python
  class Spaceship:
        # Class attribute
        tractor_beam = 'off'

        # Instance attributes
        def __init__(self, name, kind):
            self.name = name
            self.kind = kind
            self.speed = None

        # Instance methods
        def warp(self, warp):
            self.speed = warp
            print(f'Warp {warp}, engage!')

        def tractor(self):
            if self.tractor_beam == 'off':
                self.tractor_beam = 'on'
                print('Tractor beam on.')
            else:
                self.tractor_beam = 'off'
                print('Tractor beam off')
    ```
---

### **3. Instantiating Classes**
- Creating an object from a class is called **instantiation**.
- Example:
  ```python
  # Instantiate an object of the Spaceship class
  ship = Spaceship('Mockingbird', 'rescue frigate')

  # Access attributes
  print(ship.name)  # Output: Mockingbird
  print(ship.kind)  # Output: rescue frigate
    ```

---

### **4. Using Methods**
- Methods are called to perform actions or modify attributes.

#### **Example 1: Setting and Checking Warp Speed**
```python
# Set warp speed using the warp() method
ship.warp(7)

# Check speed
print(ship.speed)  # Output: 7
```

#### **Example 2: Toggling the Tractor Beam**
```python
# Toggle tractor beam using the tractor() method
ship.tractor()

# Check tractor beam status
print(ship.tractor_beam)  # Output: toggled state
```
---
## Key Takeaways

* Classes are at the core of Python, making it an object-oriented language.
* Attributes represent the characteristics of a class or object (accessed without parentheses).
* Methods are functions tied to a class that perform actions (accessed with parentheses).
* Python includes many pre-built classes, but OOP allows for high levels of customization.
* OOP knowledge is invaluable for defining your own classes and methods to analyze and manipulate data effectively.