# Style Guide

In order to ensure the legacy and lasting impact of any code written, it's important that others can understand and make use of it in the future. This UKSI style guide exists to keep our code consistent and readable.

It is based largely on [Google's Python Style Guide](https://google.github.io/styleguide/pyguide.html), so that our code aligns with what external collaborators and new recruits expect. It assumes an understanding roughly equivalent to the mid-point of EIS Code School (or an equivalent external course), and is aimed at those working on their own projects.

!!! tip "The golden rule: leave it to the linter"
    Stipulating every single formatting rule would make this a very long document. For the fine detail (semicolons, line length, indentation, blank lines, whitespace) **let the linter decide**. If in doubt on a specific point, see [Google's style guide](https://google.github.io/styleguide/pyguide.html).

## 1. Formatting your code (linting)
A **linter** automatically checks your code for a consistent format, and flags likely bugs and errors at the same time — so they're well worth using.

- Use **Black** to automatically *format* your code.
- Use **Pylint** to *check* your code for style issues and errors.

At a minimum, run Black on all scripts and notebooks. Pylint is required for scripts and recommended for notebooks. See [running a linter in VS Code](General_Guide.md#linting-formatting-code) for how to set this up, including format-on-save.

## 2. Imports
- Keep all imports at the **top** of your script, module or notebook.
- Prefer `from x import y` for the specific things you use.
- Pin versions through `pyproject.toml` and `uv.lock` so others get the same behaviour.

## 3. Naming
- Use **snake_case** for files, variables and functions (`sprint_speed`, not `SprintSpeed` or `sp1`).
- Choose **meaningful names** a sport scientist would understand — avoid single letters and cryptic abbreviations.
- **Capital letters** should only appear in **constants** (`MAX_SPEED`), **class names** (`AthleteProfile`) and **exception names**. Nothing else you write should contain capitals.

## 4. Exceptions
- Use `try`/`except` blocks to handle things that can genuinely go wrong (a missing file, a bad value), not to hide bugs.
- Catch the *specific* error you expect rather than a bare `except:`.

## 5. Global variables
- **Avoid global variables.** Pass values into functions and return results out instead — it makes code far easier to follow and reuse.

## 6. Comments and docstrings
Good documentation is what keeps code alive after you've moved on.

- **Docstrings:** every module and every function/method gets a short docstring saying *what it does*, *what it expects (inputs)* and *what it returns*.
- **Comments:** write a comment only to explain *why* something is done when the code can't show it on its own. Don't restate what the next line obviously does.

```python
def jump_height(flight_time_s: float) -> float:
    """Estimate jump height (m) from flight time using the flight-time method."""
    g = 9.81  # gravitational acceleration, m/s^2
    return g * flight_time_s**2 / 8
```

For anything not covered here, follow [Google's Python Style Guide](https://google.github.io/styleguide/pyguide.html).
