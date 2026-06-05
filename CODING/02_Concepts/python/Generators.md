tags - [[python]]

generators create iterators

**`yield` Keyword**: This replaces the traditional `return` statement. When Python encounters `yield`, it returns the specified value and **pauses** the function's execution, saving its entire state.

**State Retention**: When the generator is called again, it resumes exactly where it left off, maintaining its local variables and execution path.

