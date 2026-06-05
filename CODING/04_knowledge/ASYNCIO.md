tags - [[python]]

`asyncio` is the built-in Python library used to write concurrent code using the `async` and `await` syntax
- **Coroutines:** Functions defined with `async def` that can be paused and resumed.
- **Event Loop:** The underlying "orchestra director" that manages and distributes the execution of different tasks.
- **`async` / `await`:** Keywords used to define a coroutine and to pause execution until a result is ready, passing control back to the event Loop. 

```python
import asyncio

async def main():
    print("Hello...")
    await asyncio.sleep(1) # Simulates a waiting operation (e.g., a web request)
    print("...World!")

asyncio.run(main())
```
