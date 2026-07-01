# ISRO Hackathon Crop Monitoring Prototype

This project is a beginner-friendly prototype for crop type mapping, moisture stress detection, and irrigation advisory. It uses Python, GeoPandas, Pandas, scikit-learn, Flask, Leaflet, and Chart.js.

## Live Deployment Link

[Crop Monitoring App](https://isro-hackathon-six.vercel.app/)

## What it does
- Reads pilot area and training points from GeoJSON.
- Generates crop classification output.
- Generates moisture stress classes.
- Generates irrigation advisory values.
- Serves a dashboard with map layers and a chart.

## Folder structure
```text
isro-hackathon/
├── app.py
├── requirements.txt
├── data/
│   ├── roi.geojson
│   ├── training_points.geojson
│   ├── crop_map.geojson
│   ├── stress_map.geojson
│   ├── advisory.csv
│   └── timeseries.csv
├── templates/
│   └── index.html
└── static/
    ├── css/
    │   └── style.css
    └── js/
        └── main.js
```

## Requirements
Install Python packages:

```bash
pip install -r requirements.txt
```

## How to run

### 1. Generate outputs
Run the master pipeline:

```bash
python scripts/master_pipeline.py
```

This creates:
- `data/crop_map.geojson`
- `data/stress_map.geojson`
- `data/advisory.csv`
- `data/timeseries.csv`
- `data/crop_model.joblib`

### 2. Start the dashboard
Run the Flask app:

```bash
python app.py
```

Open the local browser URL shown in the terminal.

## Sample data
The `data/` folder contains sample files so the dashboard can run immediately:
- `roi.geojson`
- `training_points.geojson`
- `crop_map.geojson`
- `stress_map.geojson`
- `advisory.csv`
- `timeseries.csv`

## File roles

### `app.py`
Runs the Flask backend and serves the dashboard and data files.

### `templates/index.html`
Main dashboard page.

### `static/css/style.css`
Dashboard styling.

### `static/js/main.js`
Loads GeoJSON layers, switches map views, and shows the chart.

### `scripts/master_pipeline.py`
Main processing script that creates outputs from the sample input files.

## Notes
- This is a prototype for hackathon demonstration.
- The current pipeline uses placeholder features so it can run quickly.
- You can later replace the placeholder features with real satellite-derived inputs from Sentinel Hub or another EO source.

## Submission checklist
- Working Flask dashboard.
- GeoJSON outputs in `data/`.
- CSV outputs in `data/`.
- README file.
