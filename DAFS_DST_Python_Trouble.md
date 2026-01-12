# Python in R (reticulate) — Operations Cheatsheet


# 0) Mental model (what “activation” means in R)

In R, you typically **select** which Python / environment `reticulate`
binds to (via `use_*()` or `RETICULATE_PYTHON`).  
That is not the same as running `conda activate` in a shell, but the
outcome is similar: **all Python calls from R go to that interpreter**.

**Rule of thumb:** call `use_*()` (or set `RETICULATE_PYTHON`)
**before** any Python is initialized, then **restart R** if you change
it later.

------------------------------------------------------------------------

# 1) Install Python “from R”

## Option A — Install Miniconda via reticulate (recommended for most users, especially Windows)

\`\`\`r install.packages(“reticulate”) library(reticulate)

# Install a private Miniconda managed by reticulate

reticulate::install_miniconda()
