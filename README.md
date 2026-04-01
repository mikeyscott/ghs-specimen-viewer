# ghs-specimen-viewer

`ghs-specimen-viewer` is a browser-based viewer for geologic specimen outline data and associated point-density data used to render heatmap overlays. The repository contains a single HTML viewer and the JSON datasets it renders for publication-linked inspection and reuse.

## Repository Contents

- `pm_viewer_queryparam2.html`: the main viewer entry point.
- `data/all_specimens_sem390a.json`: Gulf of Mexico specimen outlines with density `x,y` data for heatmap plotting.
- `data/all_specimens_sem438n.json`: Lord Howe Rise Site 591A specimen outlines with heatmap data.
- `data/all_specimens_sem335a.json`: Cariaco Basin CAR specimen outlines with density `x,y` data for heatmap plotting.
- `data/source/`: original source CSV files used to generate the JSON datasets.
- `data/archive/`: older data files retained for reference but not used by the current viewer.

## Usage

Open `pm_viewer_queryparam2.html` in a modern web browser. The viewer reads the JSON files from the `data/` directory and renders specimen outlines together with associated density data.

The viewer accepts query parameters so a link can specify both the source dataset and the title shown above the heatmap or density plot.

URL format:

```text
pm_viewer_queryparam2.html?data=<path-to-json>&title=<url-encoded-title>
```

Parameters:

- `data`: path to the JSON file to load, relative to the HTML file.
- `title`: URL-encoded text displayed above the heatmap or density plot.

Example:

```text
https://mikeyscott.github.io/ghs-specimen-viewer/pm_viewer_queryparam2.html?data=data/all_specimens_sem390a.json&title=Source%3A%20Fig%201.A
```

This example loads `data/all_specimens_sem390a.json` and displays the title `Source: Fig 1.A`.

If your browser blocks local file access, serve the repository with a simple local HTTP server instead of opening the HTML file directly.

Example:

```bash
python3 -m http.server
```

Then open `http://localhost:8000/pm_viewer_queryparam2.html`.

## Data Notes

The current publication-facing datasets are:

- `all_specimens_sem390a.json`
- `all_specimens_sem438n.json`
- `all_specimens_sem335a.json`

These JSON files are derived from the CSV files in `data/source/`. The `data/archive/` directory contains older or superseded data that are not currently used by the main viewer.

## Authors

- Michael W. Scott: viewer development and rendering implementation.
- George H. Scott: geologic data, specimen interpretation, and manuscript authorship.

## Citation

Please cite this repository using the metadata in `CITATION.cff`. For academic use, citation of both the repository and the associated manuscript is preferred where appropriate.

## License

This repository is released under the MIT License. See `LICENSE` for details.
