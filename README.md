# glamp-review-reboot

## Project Structure

```
.
├── etc
│   ├── job         ← uncommitted task directory.
│   └── srv         ← docs, web, etc. stashed here while publication is still in press.
├── mnt
│   ├── add         ← on the deck
│   ├── bib         ← bibliography parts
│   ├── env         ← environments from which figures, tables, etc. are loaded
│   ├── fig         ← assets
│   ├── gls         ← glossary
│   ├── nfo         ← metadata, further broken down into people- and publication- prefixed files.
│   └── txt         ← the textual sources for items larger than envs which aren't extras (bib, gls, etc.).
├── run.pdf         ← output of build
├── run.tex         ← build file
├── src
│   ├── dev         ← utils, testing, etc.
│   ├── gen         ← the TeX sources required to build
│   └── opt         ← the TeX sources that can or *could* be kept optional
└── var             ← houses all temp contents
    └── tmp
```

## Details

- `etc`
- `mnt`
- `src`
    + `dev`
    + `gen`
    + `opt`
        * `cls` holds the documentclass styles and citation styles.
        * `sty` holds other layout-related material.
            * `abbrev.tex`
                * Normalizes the input of common abbreviations, for consistency.
            * `chem.tex`
                1. Provides proper rendering of certain terms, like divalent cations in LAMP.
                2. Will interact with `substances` db built from the glossary and index.
            * `siunit.tex`
                * Normalizes the input and render of scientific units.
            * `glamp-menlolike.toml`
                * Build configuration file for a font system.


## A la Carte Export

- Most elements can only be abstracted out for isolated export to a certain extent.
- After a point, decontextualization just makes things messier.
- That extent is what an `env` file contains for a given figure.

That is, if you want the figure `bst-polymerase-biology`:
1. Find `x: path/to/the/env/for/bst-polymerase-biology` (it's `\env/bst-polymerase-biology`)
2. `\input{x}`
3. Compile.

You'll get the builder's attempt to import
- the figure's assets
- the figure's textual content
- the figure's layout settings
- any dependencies on other content, ex. bibliography entries

## To Be 100% Clear:

Jeremy doesn't expect anyone to touch any TeX etc.  
He's building discrete exports of everything.

## BioRender Figure Parameters

- Biorender-produced figures are PDF. 300 ppi, 40 cm long edge — largest round size possible on export.
- No PDF options are available in biorender, ex. nothing like PDF/A conformance. You get what you get.
- I assume they at least do sufficient font subsetting for touchups to the text, but I haven't confirmed.
- We also have the source imagery used for each biorender figure — none are dynamic or data-driven.
- So you can rebuild variants more to your taste from those components, if need be.
- Components are in `/mnt/fig/components`, unless they haven't been added yet.
