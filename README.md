# DSCI 521 Computational Website

This repository contains the steps I took to build my DSCI 521 website with Quarto. It includes how I made my two computational posts using the Palmer Penguins dataset, with one post written using Python and the other written using R.

## Requirements

The following software was used to build the website:

* Quarto 1.10.18
* uv 0.12.7
* Python 3.14
* R 4.6.1

The Python environment is managed with `uv` and the committed `uv.lock` file. The R environment is managed with `renv` and the committed `renv.lock` file.

## Build instructions

Clone the repository:

```bash
git clone https://github.com/delaneywoods/delaneywoods.github.io.git
cd delaneywoods.github.io
```

All commands below should be run from the top-level repository directory.

### Set up Python

Sync the Python environment using the committed lockfile:

```bash
uv sync
```

### Set up R

Start R from the top-level repository directory:

```bash
R
```

Restore the R packages from the lockfile:

```r
renv::restore()
```

Exit R:

```r
q()
```

### Render the website

From the top-level repository directory, run:

```bash
uv run quarto render
```

## Viewing the built site

The rendered website is created in the `docs/` directory.

The main page can be opened locally at:

```text
docs/index.html
```

You can also preview the website locally with:

```bash
uv run quarto preview
```
This will remain running until you end it.

## Data

Both computational posts use the Palmer Penguins dataset from the `palmerpenguins` R/Python package.

Data source: [Palmer Penguins](https://allisonhorst.github.io/palmerpenguins/), Palmer Station Antarctica LTER.

The dataset is provided through the `palmerpenguins` package and does not require an API key or login. The computational posts load the dataset from the installed package rather than downloading it from the internet during rendering.

## Reproducibility

The Python environment is pinned using:

* `pyproject.toml`
* `uv.lock`
* `.python-version`

The R environment is pinned using:

* `renv.lock`
* `.Rprofile`
* `renv/activate.R`

To reproduce the Python environment:

```bash
uv sync
```

To reproduce the R environment:

```r
renv::restore()
```

After both environments have been restored, render the website from the repository root:

```bash
uv run quarto render
```

This should reproduce the website in the `docs/` directory.

