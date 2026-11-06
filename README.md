# Stanford Encyclopedia of Philosophy — Dump

A full export of the [Stanford Encyclopedia of Philosophy](https://plato.stanford.edu) (1,872 entries), plus the script that produced it.

## Contents

```
export/
  json/<id>.json      structured entry: metadata, TOC, main text, notes, bibliography, related entries, supplements
  md/<id>.md          the same entry rendered as a single Markdown file
  html/<id>/*.html    raw HTML: index.html plus notes and supplement pages
export_sep.py         the exporter
```

`<id>` is the SEP entry identifier, as in `https://plato.stanford.edu/entries/<id>/`.

`export/` is stored with Git LFS (~680 MB). Run `git lfs install` before cloning, or `git lfs pull` after.

## Re-running the export

```sh
pip install requests beautifulsoup4 markdownify
python export_sep.py                         # everything, skipping entries already in export/
python export_sep.py --entries spinoza kant  # specific entries
python export_sep.py --limit 10 --force      # first 10, re-fetching existing ones
```

Options: `--output-dir` (default `export/`), `--delay` (seconds between requests, default 5 per SEP's robots.txt crawl-delay). A full run takes several hours.

## License

`export_sep.py` is released into the public domain under [The Unlicense](LICENSE).

Entry content is © the Metaphysics Research Lab, Stanford University, and the respective authors. See each entry's copyright notice and the [SEP terms of use](https://plato.stanford.edu/info.html).
