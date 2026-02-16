# Step by step guide

## Install uv

Follow [this](https://docs.astral.sh/uv/getting-started/installation/#installing-uv)

## Set up a virtual environment

### Create a virtual environment
This will by default create a virtual environment directory in the current directory called `.venv`
```bash
uv venv
```

### Install the required packages
This will install TD2 to that virtual environment.

Note that the entire project is described by the [pyproject.toml](./pyproject.toml) file.

In particular, the `dependencies` list tells us that `TD2` is required, which causes it to be installed.
```bash
uv pip install .
```

### Activating the venv (Optional)
We can manually activate the virtual environment. This makes it the version of python (and by extension, all the installed packages described in the [pyproject.toml](./pyproject.toml)) that will run when we call `python` in the terminal.

```bash
source .venv/bin/activate
```

### Running code with uv
The alternative (and reommended approach, although no one around you will do this) is to run all python commands through uv.

```bash
uv run python
```

Within this directory, uv will automatically install and run the project as described by the `pyproject.toml`; this project will always run correctly via uv now if you learn to use it this way.

Technically this makes some of the previous steps redundant. If we always call python with uv in this directory, it will always create a virtual environment and maintain the packages for us with zero effort, automatically.

## TD2
We may now run TD2 by installing to the venv and activating the virtual environment or using `uv run`:

```bash
source .venv/bin/activate
```
then
```bash
TD2 --help
```
or
```bash
uv run TD2 --help
```

Both will result in:
> Please use "TD2.LongOrfs" or "TD2.Predict"

## Adding more dependencies/packages
With uv, the command is similar to pip eg:

```bash
uv add pandas
```

uv will automatically search pypi (just like pip does) and install the package.

Using `uv add` also adds it to the `pyproject.toml` such that if you were to start with a blank slate, you would re-create the exact same environment as before. Handy!
