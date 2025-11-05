
# Conda guide


## Install Miniconda (or any Conda)
```bash
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
bash Miniconda3-latest-Linux-x86_64.sh

# ... ?
yes

# Do you wish ... automatically initialize conda? ...
no
```


## Usage

### Create Conda environment
```bash
# Empty:
conda env create --name my_env --no-default-packages

# or) From file
conda env create --file my_env.yml
```


### Check if the installation was successfull ?
```bash
conda env list

# Get minimal file
conda env export --name my_env --from-history > my_env_test.yml

# or) With dependencies
conda env export --name my_env > my_env_test.yml
```

#### if not) You can remove
```bash
conda env remove -n my_env
```


### Workflow

#### then) Install, export to file
```bash
conda activate my_env
conda install new_lib
# conda env export ...
conda deactivate
```

#### or) Edit file, update changes
```bash
# Edit my_env.yml ...
conda env update -f my_env.yml --prune
```

### Then commit `my_env.yml` to share changes ...
