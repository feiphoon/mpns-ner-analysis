# MPNS NER analysis tasks

This repo contains the notebooks for all the Analysis tasks for the concerned INM363 final project submission.

## Description of contents:

Below are the stages as referenced in the report:
- A_MPNS_eda: Initial EDA of the MPNS v8 datasets (data is not present)
- B_initial_spike_of_scispacy_models: Initial exploration of scispacy pretrained models on sample abstracts
- C_initial_spike_of_spacy_models: Initial exploration of spaCy pretrained models on sample abstracts
- D_process_annotated_data_labels: Processing of gold-standard test dataset for analysis
- E_test_scispacy_on_annotated_data: Testing and analysis of scispacy models on gold-standard test data
- F_analyse_results_of_custom_blank_model:  Analysis only of custom spaCy models on gold-standard test data

Important data:

Below is a tree diagram of some of the important data held in this repo:

```
data
├── hand_annotated_abstracts
│   ├── answers
│   │   └── hand_annotated_answers.csv
│   ├── results
│   │   ├── custom_en_blank.csv
│   │   ├── en_core_sci_lg.csv
│   │   └── en_core_sci_md.csv
│   └── test
│       ├── _SUCCESS
│       └── part-00000-c89cb926-5be3-4c52-a27a-cf9d031475b9-c000.json
```

- `hand_annotated_answers.csv`: The test data converted for analysis purposes.
- `results/custom_en_blank.csv`: The test results of the custom spaCy model, transferred from an entities.html file from the NER pipeline repo.
- `results/en_core_sci_lg.csv`: The test results of the en_core_sci_lg scispacy model, formatted for analysis.
- `results/en_core_sci_md.csv`: The test results of the en_core_sci_md scispacy model, formatted for analysis.



## To run

`git clone` this repo so you can run it locally.

### Virtualenv

This repo was written for Python 3.9.8. This is important as spaCy has some problems running on some newer versions of Python. On Mac, please check your version:

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
