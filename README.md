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
mise run site   # build the PDF and assemble the GitHub Pages site
mise run clean  # remove generated files
```

## Edit the CV

- `sections/profile.tex` contains the summary and headline skills.
- `sections/experience.tex` contains the employment history.
- `sections/additional.tex` contains education, languages, community work, personal projects, and talks.
- `cv.tex` contains the page layout, reusable commands, colors, and typography.

The `\jobheading` and `\cvitem` commands keep entries consistent. Escape LaTeX's reserved characters in normal text, for example `\&`, `\%`, and `\#`.

## Published PDF

GitHub Actions builds the CV on pull requests and publishes it to GitHub Pages after every push to `main`:

- `https://cedi.github.io/cv/`
- `https://cedi.github.io/cv/Cedric_Specht.pdf`

The site root redirects to the PDF. The Pages deployment uses the `github-pages` environment, which exposes the deployed URL in the workflow run.
