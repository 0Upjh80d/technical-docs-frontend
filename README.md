# Technical Documentation for Data Analytics & AI using MkDocs Material

## Table of Contents

- [Getting Started](#getting-started)
  - [Option 1: Viewing the Deployed Documentation (Recommended)](#option-1-viewing-the-deployed-documentation-recommended)
  - [Option 2: Serving Locally](#option-2-serving-locally)
  - [Option 3: Building the Documentation](#option-3-building-the-documentation)
- [Install Dependencies](#install-dependencies)
  - [Anaconda (Recommended)](#anaconda-recommended)
  - [Poetry](#poetry)
  - [venv](#venv)

## Getting Started <a id="getting-started"></a>

We provide several options for you to access our documentation based on your needs. You may choose one or more of the following options based on your requirements.

### Option 1: Viewing the Deployed Documentation (Recommended) <a id="option-1-viewing-the-deployed-documentation-recommended"></a>

Directly head to the deployed documentation at this [link](https://0upjh80d.github.io/technical-docs-frontend/) to view the documentation. This option requires no installation of setting up and is great for non-technical stakeholders or project managers.

> [!NOTE]
> For the subsequent options, we recommend viewing the section [Install Dependencies](#install-dependencies) first.

### Option 2: Serving Locally <a id="option-2-serving-locally"></a>

Run the following command to view the documentation in `localhost`:

```bash
mkdcos serve
```

You should see the following output:

```bash
INFO    -  Building documentation...
INFO    -  Cleaning site directory
INFO    -  Documentation built in 0.69 seconds
INFO    -  [10:27:13] Watching paths for changes: 'docs', 'mkdocs.yml'
INFO    -  [10:27:13] Serving on http://127.0.0.1:8000/
```

### Option 3: Building the Documentation <a id="option-3-building-the-documentation"></a>

Alternatively, you may build the documentation with the following command:

```bash
mkdocs build
```

```bash
INFO    -  Cleaning site directory
INFO    -  Building documentation to directory: /path/to/site
INFO    -  Documentation built in 1.13 seconds
```

You should now see a folder in your root directory called `site`. This folder can be shared with internal members or across teams for portability. However, it lacks for in terms of user experience.

## Install Dependencies <a id="install-dependencies"></a>

### Anaconda (Recommended) <a id="anaconda-recommended"></a>

You can download the Anaconda Distribution for your respective operating system [here](https://docs.anaconda.com/anaconda/install/). You may also find out how to get started with Anaconda Distribution [here](https://docs.anaconda.com/anaconda/getting-started/). To verfiy your installation, you can head to the Command Line Interface (CLI) and run the following command:

```bash
conda list
```

You should see a list of packages installed in your active environment and their versions displayed. For more information, refer [here](https://docs.anaconda.com/anaconda/install/verify-install/).

---

Once set up, create a virtual environment using `conda` and install dependencies:

```bash
# Create a virtual environment
conda create -n <VENV_NAME> python=<PYTHON_VERSION> -y
conda activate <VENV_NAME>

# Install dependencies
pip install -r requirements.txt
```

### Poetry <a id="poetry"></a>

Refer to the documentation [here](https://python-poetry.org/docs/#installing-with-the-official-installer) (recommended) on how to install Poetry based on your operating system.

> [!IMPORTANT]
> For Mac users, if encountering issues with `poetry command not found`, add `export PATH="$HOME/.local/bin:$PATH"` in your `.zshrc` file in your home folder and run `source ~/.zshrc`.

---

First create a virtual environment by running the following commands:

```bash
poetry shell
```

> [!TIP]
> If you see the following error; `The currently activated Python version 3.11.7 is not supported by the project (^3.12). Trying to find and use a compatible version.`, run:
>
> ```bash
> poetry env use 3.12.3  # Python version used in the project
> ```

To install the defined dependencies for your project, just run the `install` command. The `install` command reads the [`pyproject.toml`](pyproject.toml) file from the current project, resolves the dependencies, and installs them.

```bash
poetry install
```

If there is a [`poetry.lock`](poetry.lock) file in the current directory, it will use the exact versions from there instead of resolving them. This ensures that everyone using the library will get the same versions of the dependencies.

If there is no [`poetry.lock`](poetry.lock) file, Poetry will create one after dependency resolution.

> [!TIP]
> It is best practice to commit the `poetry.lock` to version control for more reproducible builds. For more information, refer [here](https://python-poetry.org/docs/basic-usage/#:~:text=changes%20in%20dependencies.-,Committing%20your%20poetry.lock%20file%20to%20version%20control,-As%20an%20application).

---

### venv <a id="venv"></a>

You can use Python's native virtual environment `venv` to setup the project

```bash
# Create a virtual environment
python3 -m venv <VENV_NAME>
```

You can then activate the environment and install the dependencies using the following commands -

For UNIX-based systems (macOS / Linux):

```bash
# Activate virtual environment
source <VENV_NAME>/bin/activate

# Install dependencies
pip install -r requirements.txt
```

For Windows:

```powershell
# Activate virtual environment
.\<VENV_NAME>\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

> [!TIP]
> If you're using Python's native virtual environment `venv`, it is best practice to name your virtual environment `venv`.
