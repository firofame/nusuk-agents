# Nusuk Agent Directory

An independent, searchable directory of India's external agents from a saved
[public Nusuk Masar directory](https://masar.nusuk.sa/landing/services/details/2)
snapshot. This is not a live licence check or an endorsement.

**Live site:** https://firofame.github.io/nusuk-agents/

## Run locally

No dependencies or build step are required. Keep `index.html` and `data.json`
together and serve the directory over HTTP:

```sh
python3 -m http.server 8000 --bind 127.0.0.1
```

Open http://127.0.0.1:8000. Opening the HTML directly with `file://` will not
reliably load the dataset.

## Publish updates

GitHub Pages serves the repository root from the `main` branch. Commit and push
changes to `main` to deploy updates. The `.nojekyll` file enables direct static
file serving without Jekyll processing.

The site fetches `./data.json`, so it works under the `/nusuk-agents/` project
path. When updating the snapshot, preserve the dataset schema and metadata;
the site validates record totals and identifiers before displaying the data.
