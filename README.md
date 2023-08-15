# Setting up Conda and Snakemake

This code is from RomainFeron/conda_snakemake.md

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
