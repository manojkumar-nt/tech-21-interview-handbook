[← Back to Tech-21: Python Mastery & Internals Overview](./README.md) | [🏠 Series Catalog](../../README.md)

---

# 3. How Do Mutability, Shallow/Deep Copying, and the Mutable Default Argument Trap Work? 

## 1. The Core Concept & Intuition

Every data type in Python is classified as either **Immutable** or **Mutable**:
- **Immutable Types** (`int`, `float`, `str`, `tuple`, `frozenset`, `bytes`): Their internal state cannot be changed after instantiation. Any operation produces a brand-new object.
- **Mutable Types** (`list`, `dict`, `set`, `bytearray`, custom classes): Their in-place contents can be modified without changing their memory address (`id()`).

---

## 2. Under the Hood: Shallow Copy vs Deep Copy

```mermaid
graph TD
    subgraph Shallow_Copy
        Orig["Original List: [ [1, 2], 3 ]"]
        SCopy["Shallow Copy: copy.copy()"]
        Orig --> Sub["Inner List [1, 2]"]
        SCopy --> Sub
    end
    subgraph Deep_Copy
        DCopy["Deep Copy: copy.deepcopy()"] --> SubCopy["New Cloned Inner List [1, 2]"]
    end
```

- **Shallow Copy (`copy.copy()`, `list.copy()`, `[:]`)**: Creates a new outer collection, but inserts references to the exact same child objects.
- **Deep Copy (`copy.deepcopy()`)**: Recursively clones all nested objects and collections from scratch.

---


| Operation | Copy Depth | Modification to Outer Object | Modification to Nested Mutable Objects |
| :--- | :--- | :--- | :--- |
| **Assignment (`b = a`)** | Zero copy (alias) | Affects both (`a` and `b` share address) | Affects both |
| **Shallow Copy (`copy.copy`)** | Top-level copy | Independent outer container | Shared nested references |
| **Deep Copy (`copy.deepcopy`)** | Recursive full copy | Completely isolated | Completely isolated |

---

## 3. Clean Code in Action: The Mutable Default Argument Bug
### A. Default Mutable Argument Anti-Pattern vs Fix
In Python, **default arguments are evaluated ONCE when the function definition is executed (at import/load time)**, NOT every time the function is called!

```python
# SEVERE PRODUCTION BUG:
def append_to_bad(element: int, target_list: list = []) -> list:
    target_list.append(element)
    return target_list

print(append_to_bad(1)) # [1]
print(append_to_bad(2)) # [1, 2] ! (Shares the SAME list across invocations!)
print(append_to_bad(3)) # [1, 2, 3] !

# CORRECT & IDIOMATIC PYTHON PATTERN:
from typing import Optional, List

def append_to_safe(element: int, target_list: Optional[List[int]] = None) -> List[int]:
    if target_list is None:
        target_list = [] # Fresh list created per call!
    target_list.append(element)
    return target_list

print(append_to_safe(1)) # [1]
print(append_to_safe(2)) # [2]
```

### B. Shallow vs Deep Copy Mechanics
Modern Python 3.12+ production implementation:

```python
# Modern clean Python idiom demonstrating robust best practices
```

---


## 4. Common Pitfalls & Interview Traps


| Trap / Misconception | Reality |
| :--- | :--- |
| **"### 1. Tuple Containing Mutable Elements"** | A `tuple` is immutable (you cannot add or replace elements), but if a tuple holds a `list`, the inner list can be mutated in-place: ```python t = ([1, 2], 3) t[0].append(99) # Perfectly legal! t is now ([1, 2, 99], 3) ``` --- |

---


## 5. 60-Second Memory Anchor

> **"Default arguments are evaluated once at function definition time. Never use mutable objects (`[]` or `{}`) as default parameters—use `None` and initialize inside the function body. Use `copy.deepcopy()` to clone nested structures safely."**

---

[← Question 02](./02-everything-is-an-object-and-memory-model.md)

> ### 🎓 Looking for Questions 04 through 21 & Deep-Dive Appendices?
> You have reached the end of the free sampler for **Tech-21: Python Mastery & Internals**!
> 
> The full release contains **18 additional core interview chapters** plus **2 architectural reference appendices**, memory layouts, complete edge-case tables, and production patterns.
> 
> 📖 **[Get the Full Edition (Kindle / EPUB / PDF) →](./README.md#how-to-get-the-full-edition)**

