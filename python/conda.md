conda
=====

Download
--------------------------------------------------

Download the installer [here](http://conda.pydata.org/miniconda.html).


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

Update conda:

```bash
conda update conda
```

Update python:

```bash
conda update python
```