# pretrained-model-comparison

This repo contains the pretrained model comparison notebooks to kick off the project.

## To run

`git clone` this repo so you can run it locally.

### Virtualenv

This repo was written for Python 3.8.5. This is important as spaCy has some problems running on some newer versions of Python. On Mac, please check your version:

```
python --version
```

Having a virtual environment gives you a self-contained space to reproduce your project with the right versions of modules. `venv` is the simplest way toward this.

Depending on if the notebook you are running is using spaCy or scispacy, you will have to switch virtual environments. Create a separate virtual environment for either.

Create your new virtual environment. Clone this repo, then:
```
cd inm363-individual-project/pretrained-model-comparison # Be in your repo folder
python3 -m venv venv-scispacy # Where venv is the name of your new environment
```

Start and set up your new environment:
```
source venv-scispacy/bin/activate
pip install -r scispacy_requirements.txt # Install the required packages in your new environment
pip list # Optional: check what was installed in `venv`
```

Exit your environment:
```
source deactivate
```

### TODO: Docker image

### VSCode setup:

Create `.vscode/settings.json` in the root project folder, with the following contents (replacing the `pythonPath`):
```
{
    "python.terminal.activateEnvironment": true,
    "python.linting.enabled": true,
    "python.linting.pylintEnabled": false,
    "python.linting.flake8Enabled": true,
    "python.linting.flake8Args": [
        "--config",
        ".flake8"
    ],
    "python.formatting.provider": "black",
    "editor.formatOnSave": true,
    "python.pythonPath": "/Users/fei/projects/inm363-individual-project/pretrained-model-comparison/venv/bin/python3"
}
```
