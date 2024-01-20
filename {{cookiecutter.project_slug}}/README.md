# {{cookiecutter.project_name}}
Project created by {{cookiecutter.author}}.

## Prerequisites
Install [pipx](https://github.com/pypa/pipx):
```
python3 -m pip install --user pipx
python3 -m pipx ensurepath
```

Install [Poetry](https://python-poetry.org/)
```
pipx install poetry
```

Install [pyenv](https://github.com/pyenv/pyenv):
```
curl https://pyenv.run | bash
```

## Installation
This section assumes you have just created a new project from the template, and that you are in the root of the project, i.e. you just ran:
```
cookiecutter gh:/VanderpoelLiam/cookiecutter-python 
cd {{cookiecutter.project_slug}}
```
First initialise this project as a Git repository:
```
git init
git add . 
git commit -m "Initial commit"
```

Setup the Python 3.10.12 environment with:
```
pyenv install 3.10.12 
pyenv virtualenv 3.10.12 {{cookiecutter.package_name}}
pyenv local {{cookiecutter.package_name}} 
```

Setup Poetry:
```
poetry init --dev-dependency pre-commit --dev-dependency pytest --python 3.10.12

# Optionally add project dependencies, this can also be done later
poetry add pandas 
poetry add --group dev pytest-cov

poetry install
```

Install pre-commit
```
poetry run pre-commit install
```

## Usage
To run a script:
```
poetry run python your_script.py
```

Similarly for commandline tools, notably testing with pytest, you can run:
```
poetry run pytest
```
