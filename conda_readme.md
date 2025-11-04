
# Conda + Jupyter guide

## Install

### Download Jupyter extension for VS Code
```bash
code --install-extension ms-toolsai.jupyter
```

### Download and install Miniconda
```bash
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
bash Miniconda3-latest-Linux-x86_64.sh

# Do you wish ... automatically initialize conda? ...
no
```

## Usage

### Create Conda environment 'env'
```bash
# Empty:
conda env create -f env.yml

# Or from file:
conda create -n env --file env.yml --no-default-packages
```


### Workflow

#### Like this:
```bash
conda activate env
conda install new_lib
conda env export > env.yml
```

#### Or like that:
```bash
# Add new_lib to env.yml ...
conda env update -f env.yml --prune
```

#### Then commit `env.yml` to share changes ...