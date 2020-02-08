# Environment creation with conda

#### Creating environment
```
conda create -n conda-env python=3.7            # or use --name
conda activate conda-env                                   # activate environment
conda deactivate                                                  # deactivate environment
```
Conda environments live in the `/Users/user-name/.conda/envs` or `./Anaconda3/envs` if created as administrator.

**Note:** just like venv, environments can be created directly in the project folder (so outside of Anaconda's envs folder) with the following command:
```
conda create -p /path/to/conda-env                # or use --prefix
```
**Note:** conda can no longer activate the environment with the `--name` flag. Instead the environment has to be activate with the full path `/path/to/conda-env`.

To fix the environment display, the `env_prompt` setting in the `.condarc` file need to be modified with the following command:
```
conda config --set env_prompt '({name})'
```
![See conda's configuration documentation here](https://conda.io/projects/conda/en/latest/user-guide/configuration/index.html).

#### Installing packages
##### Installation from the Anaconda repository
The targeted environment needs to be activated first.
```
conda install pandas                    # installation of 🐼 from Anaconda repository
conda install pandas=1.0.1         # installation of a specific version
```
Packages installation can also be made from the default shell with the following command:
```
conda install -n conda-env pandas                           # with the environment name
conda install -p /path/to/conda-env pandas          # with the path to the environment
```

##### Installation from other Conda repositories
Packages can also be installed from other repositories.
To install a package from a third party repository like Conda-Forge, the channel flag `--channel` or `-c` must be used.
```
conda install -c conda-forge opencv                       # or use --channel
```

##### Installation from PyPi
```
pip install requests
```

#### Updating packages
```
conda update                                                                   # updates all the packages installed in the environment
conda update pandas                                                     # from the activated environment
conda update -n conda-env pandas                            # with the environment name
conda update -p /path/to/conda-env pandas           # with the path to the environment
```

#### Removing packages
```
conda remove seaborn
```

#### Packages management
```
conda search -f seaborn                                  # search for all the available versions of a certain package

```

#### Python
```
conda search -f python                                           # list out the available Python versions 🐍
conda install python=3.7                                        # install a specific python version
conda update python                                              # update the current Python version
```

#### Jupyter
```

```

#### More commands
```
conda --version                          # check conda's current version

conda info                                   # get a detailed list of information


conda env list                                                                                               # display the list of conda environments. A * shows the current activated environment
conda list                                                                                                      # list installed packages in the current environment
conda list -n conda-env                                                                              # list packages installed with name
conda list -p /path/to/conda-env                                                             # list packages installed with path
conda env export -f environment.yml                                                     # or use --file. Make an environment file
conda env create -n conda-env -f /path/to/environment.yml            # create an environment from the environment file
conda env update -n conda-env -f /path/to/environment.yml           # update an environment with the environment file
```

#### My favorite routine
```
conda create -n conda-env python=3.7            # or use --name
conda activate conda-env
conda info
conda env list
conda update python
conda update --all --yes
conda install ipykernel
ipython kernel install --user --name=conda-env
jupyter notebook --ip=0.0.0.0 --no-browser

pip install numpy
pip install pandas
pip install seaborn
pip install scikit-learn
pip install matplotlib

conda update --all --yes
```
