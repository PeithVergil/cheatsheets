conda
=====

Download
--------------------------------------------------

Download the installer [here](https://conda.io/miniconda.html).


Environments
--------------------------------------------------

Create a new virtual environment:

```bash
conda create --name [myenv] python
```

Remove a virtual environment:

```bash
conda remove --name [myenv] --all
```

List all virtual environments:

```bash
conda info --envs
```

Activate a virtual environment:

```bash
source activate [myenv]
```

Deactivate a virtual environment:

```bash
source deactivate
```

Packages
--------------------------------------------------

List packages installed in the current virtual environment:

```bash
conda list
```

List packages installed in a specific virtual environment:

```bash
conda list --name [myenv]
```

Install a package:

```bash
conda install [package]
```

Install a package from a different channel (conda-forge):

```bash
conda install [package] -c conda-forge
```

Search for a package from a different channel (conda-forge):

```bash
conda search [package] -c conda-forge
```

Install a package to a specific virtual environment:

```bash
conda install --name [myenv] [package]
```

Update the "conda" package:

```bash
conda update conda
```

Update the "python" package:

```bash
conda update python
```

Uninstall a package:

```bash
conda uninstall [package]
```