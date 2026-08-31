# Cedric Specht's CV

This repository contains the editable LaTeX source for the CV and a reproducible PDF build. The layout follows the previous Word-exported PDF, while the content is split into small section files so routine updates do not require touching the formatting code.

## Build the PDF

[mise](https://mise.jdx.dev/) is the only prerequisite. It installs the pinned TinyTeX distribution declared in `mise.toml`; the setup task then installs the required LaTeX packages through TinyTeX's package manager.

```sh
mise install
mise run build
```

The rendered CV is written to `output/pdf/Cedric_Specht.pdf`.

Other useful tasks:

```sh
mise run setup  # install or update the required TeX packages
mise run clean  # remove generated files
```

## Edit the CV

- `sections/profile.tex` contains the summary and headline skills.
- `sections/experience.tex` contains the employment history.
- `sections/additional.tex` contains education, languages, community work, personal projects, and talks.
- `cv.tex` contains the page layout, reusable commands, colors, and typography.

The `\jobheading` and `\cvitem` commands keep entries consistent. Escape LaTeX's reserved characters in normal text, for example `\&`, `\%`, and `\#`.

## Continuous integration

GitHub Actions builds the CV on every push to `main`, on pull requests, and when started manually. Each run uploads `Cedric_Specht.pdf` as a workflow artifact.
