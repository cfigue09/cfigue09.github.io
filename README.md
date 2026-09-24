# Cesar Figueroa MDS website

This is my website for the UBC Master of Data Science program.
It includes a post about my first weeks in MDS and two analyses
using Palmer Penguins data, one in Python and one in R.

My website: https://cfigue09.github.io

## Tools I used

You need Git, Quarto, uv, and R installed.

These are the versions I used:

- Quarto 1.10.18
- uv 0.12.5
- R 4.6.1
- Python 3.14

The Python package versions are saved in `uv.lock`.
The R package versions are saved in `renv.lock`.

## How to build the website

First, open a terminal in the folder where you want to save
the project. Download the repository and enter its folder:

```bash
git clone https://github.com/cfigue09/cfigue09.github.io.git
cd cfigue09.github.io
```

Run all the remaining commands from this project folder.

Install the Python dependencies:

```bash
uv sync --locked
```

Restore the R packages:

```bash
Rscript -e 'renv::restore(prompt = FALSE)'
```

The project uses `.Rprofile` to start renv automatically.
It will install renv if needed.

Build the website:

```bash
uv run quarto render
```

The website files are created in `docs/`.
Make sure the file needed for GitHub Pages is there:

```bash
touch docs/.nojekyll
```

To see the website on your computer, run:

```bash
uv run quarto preview
```

Open the local address shown in the terminal.
Use Control+C to stop the preview.

## About the data

I used [Palmer Penguins](https://allisonhorst.github.io/palmerpenguins/)
for both posts. The data were collected by Dr. Kristen Gorman
and Palmer Station Antarctica LTER. The data license is CC0.

Package citation: Horst AM, Hill AP, Gorman KB (2020).
palmerpenguins: Palmer Archipelago (Antarctica) penguin data.
https://doi.org/10.5281/zenodo.3960218

The data come with the palmerpenguins packages in Python and R.
You need internet to download the repository and install the packages.
The posts do not download data when the code runs.

## Updating the live website

GitHub Pages uses the files in `docs/`.
After making changes, I need to render the website again,
check `docs/.nojekyll`, and commit and push the updated files.