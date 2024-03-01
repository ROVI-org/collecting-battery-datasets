# Collecting Battery Datasets

Scripts for downloading and standardizing data used by ROVI modeling teams

## Installation

The main requirements are [`battery-data-toolkit`](https://github.com/ROVI-org/battery-data-toolkit) and Jupyter.
Some tasks, such as gathering data from Matr, require additional libaris.

The toolkit is undergoing rapid development, so we recommend installing the latest version from Github.

The provided [Anaconda Environment File](./environment.yml) builds with the latest toolkit and dependencies for each task:

```bash
conda env create --file environment.yml --force
```
