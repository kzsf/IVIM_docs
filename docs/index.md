# IVIM_fit
Preprocessing diffusion MRI data and fitting IVIM models

## How to use locally:
1. Clone the repository with `git clone` and `cd` into it. You should see a `run.py` file there.
```
git clone https://github.com/PostonLab/IVIM_fit.git
```
```
cd ivim_fit
```
2. Install poetry using `pip install poetry`
```
pip install poetry
```
3. Install dependencies with `poetry install`, then use `poetry shell` to activate the virtual environment.
```
poetry install
```
```
poetry shell
```
4. First run the workflow dry-run with python `./run.py <path to bids data> <path to output> participant -np`.
```
./run.py <insert path to your bids data> <insert path to your output> participant -np
```
5. If the dry run is successful, we can run the workflow with `python ./run.py <path to bids data> <path to output> participant -c all --use-singularity`. Where `-c` is for number of cores you want to use. `all` will use everything available.
```
python ./run.py <path to bids data> <path to output> participant -c all --use-singularity
```
6. When running for the first time, it will install all the singularity containers.

## How to run in Sherlock cluster at Stanford:
1. Activate an interractive shell using `salloc`
```
salloc
```
2. Load python3 using `ml python/3.9.0`
```
ml python/3.9.0
```
3. Create a python environment `python3.9 -m venv py3`
```
python3.9 -m venv py3
```
4. Activate the environment `source py3/bin/activate`
```
source py3/bin/activate
```
6. Install dependencies with `poetry install`.(If poetry is not installed, install it using `python3 -m pip install poetry==1.8.5`. If needed install six package using `python3 -m pip install six`)
```
poetry install
```
``` title="If poetry not already installed:"
python3 -m pip install poetry==1.8.5
```
7. Deactivate the existing python environment using `deactivate`. Then use `poetry shell` to activate the new ivim virtual environment.
```
deactivate
```
```
poetry shell
```
8. Navigate to `ivim_fit` directory using `cd ivim_fit` where you will see the `run.py` file.
```
cd ivim_fit
```
9. First run the workflow dry-run with `python ./run.py <path to bids data> <path to output> participant -np`.
```
python ./run.py <path to bids data> <path to output> participant -np
```
10. If the dry run is successful, we can run the workflow with `python ./run.py <path to bids data> <path to output> participant -c all --use-singularity`. Where `-c` is for number of cores you want to use. `all` will use everything available.
```
python ./run.py <path to bids data> <path to output> participant -c all --use-singularity
```
11. If running again, first load python 3.9 using `ml python/3.9.0`, and then run `poetry shell` to activae the python environment.
```
ml python/3.9.0
```
```
poetry shell
```

## How to contribute:
1. Clone the repository with `git clone https://github.com/PostonLab/IVIM_fit.git`
```
git clone https://github.com/PostonLab/IVIM_fit.git
```
2. Checkout a branch and make changes.
3. Before doing `git add .`, run `poe quality`. This will automatically run formatting and make necessary changes.
4. If everything looks pretty, proceed with pushing changes.
5. Go to github and make a pull request for your changes.

## Acknowledgement
This project utilizes code adapted from the snakedwi pipeline ([https://github.com/akhanf/snakedwi]), an open-source project for diffusion MRI preprocessing. Their work provided a valuable foundation for building the preprocessing steps of IVIM_fit pipeline.









