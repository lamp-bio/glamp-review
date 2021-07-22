# glamp-review-reboot

## Project Structure

```
.
├── etc
│   ├── job ← uncommitted task directory.
│   └── srv ← docs, web, etc. stashed here while publication is still in press.
├── mnt
│   ├── add ← on the deck
│   ├── bib ← bibliography parts
│   ├── env ← environments from which figures, tables, etc. are loaded
│   ├── fig ← assets
│   ├── gls ← glossary
│   ├── nfo ← metadata, further broken down into people- and publication- prefixed files.
│   └── txt ← the textual sources for items larger than envs which aren't extras (bib, gls, etc.).
├── run.pdf ← output of build
├── run.tex ← build file
├── src
│   ├── dev ← utils, testing, etc.
│   ├── gen ← the TeX sources required to build
│   └── opt ← the TeX sources that can or *could* be kept optional
└── var ← houses all temp contents
    └── tmp
```
