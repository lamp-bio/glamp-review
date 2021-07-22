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


