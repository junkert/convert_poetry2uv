# poetry_to_uv

The poetry_to_uv.py script is meant to easily set the base for the pyproject.toml to be consumed by `uv` instead of `poetry`.

**It is not foolproof!**

It has a dry-run flag, to have a temporary file to validate the output. When not running the dry-run the original file is saved with a .org extension.

    uv run poetry_to_uv.py <path to file> [-n]

You may need to make some manual changes, probably around the following:

* tool sections that use the multiline syntax in the exclude assignments (ruff, mypy, black, ...)
* if you had optional dev groups, the dev group libraries will be used, the optional flag is removed

# Using as a tool
The script can be run as a tool using [`uvx`](https://docs.astral.sh/uv/guides/tools/)

    uvx --from git+https://github.com/bartdorlandt/poetry_to_uv poetry-to-uv --help

# Contribute
Feel free to contribute to the code.

Cheers, Bart Dorlandt