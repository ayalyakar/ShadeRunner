# Sources

Raw sourcebook page screenshots cited by files in `Data/`.

## Layout

`Sources/<Edition-and-Book>/pNNN-<slug>.png` — one file per page. Page numbers are the *printed* sourcebook page numbers, not the scan's image index.

## Current archive

### SR1E-Seattle (Shadowrun 1E — Seattle Sourcebook, FASA, 1990)

- `p001-cover.png` — cover.
- `p002-toc-1.png` — Table of Contents, page 1 of 3.
- `p003-toc-2.png` — Table of Contents, page 2 of 3.
- `p004-toc-3.png` — Table of Contents, page 3 of 3.
- `p005-introduction.png` — Introduction chapter opener.

## Citation format (in `Data/` YAML)

```yaml
sources:
  - edition: SR1E
    book: "Seattle Sourcebook"
    year: 1990
    page: 131
    image: "Sources/SR1E-Seattle/p131-redmond-crime.png"
    section: "Redmond / Crime"
```
