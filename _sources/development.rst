Development
===========

Code Formatting
---------------

This project uses `ruff <https://github.com/astral-sh/ruff>`_ for code formatting and linting. Ruff is a fast Python linter and formatter written in Rust that combines the functionality of multiple Python linting tools.

To format your code:

.. code-block:: bash

    # Format code
    hatch run lint:fmt

    # Check code without modifying
    hatch run lint:check

Pre-commit hooks are also configured to automatically format and lint code before commits.

Linting Rules
-------------

The project enforces the following rule sets:

- **B**: flake8-bugbear - Finds likely bugs and design problems
- **C**: flake8-comprehensions - Helps write better list/set/dict comprehensions
- **E**: pycodestyle errors - PEP 8 style guide errors
- **F**: pyflakes - Detects various errors
- **W**: pycodestyle warnings - PEP 8 style guide warnings
- **I**: isort - Import sorting
- **N**: pep8-naming - PEP 8 naming conventions
- **D**: pydocstyle - Docstring style checking
- **UP**: pyupgrade - Upgrade syntax for newer Python
- **B9**: flake8-broken-line - Checks for broken line continuation
- **BLE**: flake8-blind-except - Checks for blind except statements
- **COM**: flake8-commas - Trailing comma enforcement
- **SIM**: flake8-simplify - Code simplification suggestions
- **ARG**: flake8-unused-arguments - Unused function arguments
- **ERA**: eradicate - Commented out code detection
- **PL**: pylint - General Python linting
- **RUF**: ruff-specific rules

IDE Integration
---------------

For the best development experience, configure your IDE to use ruff for formatting and linting:

VS Code
~~~~~~~

Add to your settings.json:

.. code-block:: json

    {
        "editor.formatOnSave": true,
        "python.linting.enabled": true,
        "python.linting.flake8Enabled": false,
        "python.linting.mypyEnabled": true,
        "python.formatting.provider": "none",
        "editor.defaultFormatter": null,
        "editor.codeActionsOnSave": {
            "source.fixAll.ruff": true,
            "source.organizeImports.ruff": true
        },
        "[python]": {
            "editor.defaultFormatter": "charliermarsh.ruff"
        }
    }

PyCharm
~~~~~~~

Install the "Ruff" plugin from the JetBrains Marketplace and configure it to run on save.
