# vcRichard.github.io

Personal GitHub Pages site built with Quarto. It has two blog posts analysing the Palmer Penguins data, one written in R and one in Python and one post talking about my initial impressions. The site is published at https://vcrichard.github.io.

## What to install first

Versions used to build the site:

- [Quarto](https://quarto.org/docs/get-started/) 1.10.18
- [uv](https://docs.astral.sh/uv/) 0.12.7. uv installs the pinned Python (3.14, from `.python-version`) by itself.
- [R](https://cran.r-project.org/) 4.6.1

You do not need to install `renv` yourself. The first time R starts in this project, `.Rprofile` installs it, which needs an internet connection.

## Build the site

Run these in order, starting from a terminal in the folder where you want the repository.

In the terminal run:

```
git clone https://github.com/vcRichard/vcRichard.github.io.git
cd vcRichard.github.io
uv sync
```

`uv sync` builds the Python environment `.venv` from `uv.lock`.

In R (I recommend Rstudio but any R environment should work), set the working directory to the top level of the repository (vcRichard.github.io). The easiest way is to open the Rproject file `vcRichard.github.io.Rproj` in the repository. Then in the console run:

```
renv::restore()
```

Answer `y` if renv asks for permission. This installs the R packages listed in `renv.lock`.

Back to the terminal, make sure the working directory is vcRichard.github.io and run:

```
uv run quarto render
```

## Where the built site is

Rendering the site writes the html file to the `docs/` folder. Open `docs/index.html` in a browser or run `uv run quarto preview` to view it locally.

## Data

Both posts use the Palmer Penguins data ([Palmer Station Antarctica LTER](https://allisonhorst.github.io/palmerpenguins/), CC0 licence). It comes bundled with the `palmerpenguins` package for both development languages so no network connection required.
