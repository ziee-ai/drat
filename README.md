# ziee-ai drat archive

R packages from [ziee-ai](https://github.com/ziee-ai), distributed as a
[drat](https://github.com/eddelbuettel/drat) archive and served via GitHub Pages at
<https://ziee-ai.github.io/drat/>.

## Available packages

| Package | Description | Source |
|---|---|---|
| `mcpserver` | Model Context Protocol server SDK for R | [mcpserver-r](https://github.com/ziee-ai/mcpserver-r) |
| `rcpa.mcpserver` | MCP server exposing the RCPA bioinformatics toolkit | [rcpa-mcpserver](https://github.com/ziee-ai/rcpa-mcpserver) |
| `dscc.mcpserver` | MCP server for the DSCC cancer-subtyping method | [dscc-mcpserver](https://github.com/ziee-ai/dscc-mcpserver) |

## Install

```r
install.packages("mcpserver",
                 repos = c("https://ziee-ai.github.io/drat", getOption("repos")))
```

Include CRAN (via `getOption("repos")`) so dependencies resolve. All packages are
pure R, so the source tarballs install on Linux, macOS, and Windows alike.

`rcpa.mcpserver` and `dscc.mcpserver` depend on `mcpserver`, which is pulled from
this drat automatically. Their analysis tools additionally need Bioconductor
packages (e.g. `SummarizedExperiment`, `limma`, `DESeq2`, `edgeR`) — install those
separately via `BiocManager`.

## Publishing a package

Each source repo's `.github/workflows/release.yml` builds, `R CMD check`s, and
publishes to this drat on a `v*` tag (via `drat::insertPackage` → push to
`gh-pages`). To add one manually from a local `gh-pages` checkout:

```r
drat::insertPackage("<package>_<version>.tar.gz",
                    repodir = "<path-to-gh-pages-checkout>")
```

Commit the updated `src/contrib/` index on `gh-pages` and push.
