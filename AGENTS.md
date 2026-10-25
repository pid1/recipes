# AGENTS.md

## Sadr

### Build and test
- The repo has no tests. The check is the CI build, which must exit 0 and write `recipes.pdf`: `pandoc -f gfm -t pdf --pdf-engine=xelatex --template=template.tex -o recipes.pdf recipes.md`
- On Ubuntu, install the build tools first, as `.github/workflows/build.yaml` does: `sudo apt-get install -y --no-install-recommends pandoc texlive-xetex texlive-fonts-recommended texlive-latex-extra fonts-texgyre`
- Never run the "Determine next release version" and "Create release" steps locally. On a push to `main`, they tag the next `v<N>` and publish `recipes.pdf` as a GitHub release.

### Toolchain
- The repo has no package manager and no lockfile. CI installs pandoc and TeX Live from the runner's apt index.
