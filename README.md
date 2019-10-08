### Conda
A group of notes to manage packages with Anaconda under Supercomputing Cluster

# Changing Directories to store conda environments

```module purge
module load compiler/intel/2017
module load anaconda/2019.03
module load nwchem/6.8.1-cpu
module list´´´
##############################################################
# List conda envs
##############################################################
```conda env list´´´
##############################################################
# Remove isicle env is previously created
##############################################################
```conda env remove --name isicle
conda clean --yes --all´´´
##############################################################
# Set 
##############################################################
```echo "export CONDA_ENVS_PATH=/scratch/${USER}/conda_envs" >> ~/.bashrc
echo "export CONDA_PKGS_DIRS=/scratch/${USER}/conda_pkgs" >> ~/.bashrc
source ~/.bashrc´´´
##############################################################
# Create conda env
##############################################################
```conda create -n isicle -c conda-forge -c bioconda -c ambermd openbabel rdkit ambertools snakemake numpy pandas yaml statsmodels´´´ python=3

