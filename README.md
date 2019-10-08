# Conda
A group of notes to manage packages with Anaconda under Supercomputing Cluster

## Changing Directories to store conda environments
- Loading modules
```module purge
module load compiler/intel/2017
module load anaconda/2019.03
module load nwchem/6.8.1-cpu
module list
```

Then, we check the list of environments

```conda env list
```

- Remove old env previously created

```conda env remove --name oldenv
conda clean --yes --all
```
- Setting the new addreses to store the environments

```echo "export CONDA_ENVS_PATH=/scratch/${USER}/conda_envs" >> ~/.bashrc
echo "export CONDA_PKGS_DIRS=/scratch/${USER}/conda_pkgs" >> ~/.bashrc
source ~/.bashrc
```
- Reinstalling environment with list of programs

```conda create -n isicle -c conda-forge -c bioconda -c ambermd openbabel rdkit ambertools snakemake numpy pandas yaml statsmodels python=3
```
