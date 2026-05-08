# Jupyter AI Lab

A Jupyter/Micromamba AI sandbox for experimenting with multiple AI models in isolated environments. Run, test, and compare models without dependency conflicts, system breakage, or messy setups.  Everything is reproducible and easy to clean up.

---

### Install micromamba
```bash
curl -Ls https://micro.mamba.pm/install.sh | bash
source ~/.bashrc
```

### Create Jupyter environment
```bash
micromamba create -n jupyter python=3.11 jupyterlab -c conda-forge
```

### Access Jupyter
```bash
micromamba activate jupyter
jupyter lab
```

### Add AI model
```bash
micromamba create -n [MODEL-NAME] python=3.10 ipykernel -c conda-forge
micromamba activate [MODEL-NAME]
pip install [PACKAGE]
python -m ipykernel install --user --name [MODEL-NAME] --display-name "AI: [MODEL-NAME]"
```

### Remove AI model
```bash
jupyter kernelspec remove [MODEL-NAME]
micromamba env remove -n [MODEL-NAME]
micromamba clean --all
```

### List all environments
```bash
micromamba env list
```
