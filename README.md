# Spotify ETL Pipeline

## Project Summary

This repository implements an **Extract-Transform-Load (ETL) pipeline** that retrieves data from the **Spotify Web API**, performs transformations, and outputs cleaned datasets. The pipeline is intended for **data engineering experimentation and analytics** workflows.

## Repository Structure
```bash
.
├── Data/
├── Architecture.jpeg
├── extract_spotify_data.py
├── transform_spotify_data.py
├── main_script.ipynb
├── spotipy_layer.zip
└── README.md
```

**Notes on contents:**
- `extract_spotify_data.py`: Script to request data from Spotify API.  
- `transform_spotify_data.py`: Script to transform raw Spotify API responses into analysis-ready tables.  
- `main_script.ipynb`: Notebook with example usage or development exploration.  
- `Data/`: Directory for storing staged/raw/transformed outputs.  
- `Architecture.jpeg`: Visual of the pipeline architecture.  
- `spotipy_layer.zip`: Dependency bundle for AWS Lambda or similar runtimes.

## Requirements

### Python Dependencies

Install packages required for extraction and transformation:

```bash
pip install spotipy pandas numpy
```
If additional dependencies are used in the code, install them explicitly.

## Environment Configuration
The pipeline uses credentials for the Spotify Web API. Set the following environment variables prior to execution:
```bash
SPOTIFY_CLIENT_ID=<your Spotify Client ID>
SPOTIFY_CLIENT_SECRET=<your Spotify Client Secret>
```

# Usage Extraction

Run the extraction script to collect data from Spotify API:
```bash
python extract_spotify_data.py
```

python extract_spotify_data.py
Output will be written to local storage under Data/ (structure determined by script).
Insufficient data to verify output folder names and exact format.

Transformation
Transform raw extraction output into cleaned datasets:

```bash
python transform_spotify_data.py
```

Transformed results are saved under Data/ in structured files.
Insufficient data to verify exact schema and file naming.

# Notebook
Use main_script.ipynb for development, testing, visualization, or step-by-step pipeline execution.

# Architecture
The pipeline follows standard ETL stages:
- Extract: Call Spotify API and save raw JSON.
- Transform: Process and normalize into structured tables (artists, tracks, etc.).
- Load/Store: Persist cleaned data to local storage or downstream systems.

Refer to `Architecture.jpeg` for a diagram of component interactions.

# Extensions & Deployment
Typical extensions include:
- Scheduling via Airflow or cron.
- Cloud integration (AWS Lambda, S3, Glue, Athena).
- Insufficient data to verify any pre-configured cloud deployment in this repo.
