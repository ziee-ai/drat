# ziee-ai drat archive

R packages from [ziee-ai](https://github.com/ziee-ai), distributed as a
[drat](https://github.com/eddelbuettel/drat) archive and served via GitHub Pages at
<https://ziee-ai.github.io/drat/>.

## Available packages

_No packages published yet._

## Install

```r
install.packages("<package>",
                 repos = "https://ziee-ai.github.io/drat")
```

On macOS / Windows you can request pre-built binaries:

```r
install.packages("<package>",
                 repos = "https://ziee-ai.github.io/drat",
                 type  = "binary")
```

## Publishing a package

Build the package tarball, then add it to the `gh-pages` branch using the
[`drat`](https://github.com/eddelbuettel/drat) package and push:

```r
drat::insertPackage("<package>_<version>.tar.gz",
                    repodir = "<path-to-gh-pages-checkout>")
```

Commit the updated `src/contrib/` index on `gh-pages` and push.
