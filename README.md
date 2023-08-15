# Setting up Conda and Snakemake

## Install Conda

Full instructions available [here](https://conda.io/projects/conda/en/latest/user-guide/install/linux.html).

**Download the installer script and run it:**

```bash
wget https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh
bash Miniconda3-latest-Linux-x86_64.sh
```

Follow instructions from the prompt. 

**Restart your shell:**

```bash
source ~/.bashrc
```

**Note:** If you're not using bash as your shell, source the appropriate file (*e.g.* `~/.zshrc` if you're using zsh)

**Initialize conda for your shell:**

```bash
# Replace bash with whatever shell you are using
conda init bash
```

**Update conda:**

The Conda version from the official installer is not always the latest update. To make sure Conda is up-to-date, run:

```bash
conda update conda
```

**Install mamba:**

Mamba is a faster, more efficient drop-in replacement for the `conda` executable. It is advised to use it to install packages and it's used by default by Snakemake.

```bash
conda install -n base -c conda-forge mamba
```

## Install Snakemake

The recommended way to install and run Snakemake is to create a conda environment specifically for it:

```bash
# Create a new empty environment called "snakemake"
conda create --name snakemake
# Activate the environment "snakemake"
conda activate snakemake
# Install snakemake from the Bioconda channel (conda-forge contains dependencies)
mamba install -c conda-forge -c bioconda snakemake
```

You can now activate the environment snakemake and run snakemake from it. It is advised to keep the environment as clean as possible, *i.e.* only install software related to running snakemake.

## Running Snakemake with a scheduler (cluster)

To run Snakemake on HPC platforms using a scheduler, it is recommended to use a Snakemake profile. An "official" collection of profiles for the most popular schedulers are available [here](https://github.com/snakemake-profiles/doc).

If you're running some of my own Snakemake pipelines on an HPC platform with Slurm, I recommend using my own Slurm profile available [here](https://github.com/RomainFeron/snakemake-slurm).
