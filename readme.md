# LinkedIn Phishing Detection & URL Analysis

This project automates the detection of phishing URLs from LinkedIn messages and performs detailed URL analysis. It processes CSV files containing LinkedIn messages, extracts URLs, analyzes them, and saves the results in an Excel file. It includes visual feedback during processing through a rotating loader animation and ensures files are processed only once.

## Features

- **Automated URL Extraction**: Extracts URLs from the `CONTENT` column of CSV files containing LinkedIn messages.
- **Continuous File Monitoring**: Watches the `input` folder for new CSV files and processes them automatically.
- **Phishing URL Analysis**: Analyzes each extracted URL for potential phishing risks using the `url_analyser` module.
- **Loading Animation**: Displays a rotating loader during long processes such as extraction and analysis.
- **Results in Excel Format**: Saves the analysis results to an Excel file, excluding `.csv` from the filename.
- **Processed File Logging**: Tracks processed files to prevent reprocessing of the same file.
- **Internet Connection Monitoring**: Automatically checks for an active internet connection before starting and retries until it’s restored.

## Project Structure

```bash
.
├── input/                      # Folder containing input CSV files for processing.
│   └── messages.csv             # Example CSV file with LinkedIn messages.
├── output/                     # Folder where the analysis results are saved.
│   └── url_analysis_results.xlsx # Example output file.
├── processed_files.log          # Log file to track processed CSV files.
├── url_analyser.py              # Custom URL analysis module.
├── app.py                       # Main script for running the project.
├── README.md                    # Project documentation.
```

## How It Works

1. **Input CSV Files**: The system expects CSV files with LinkedIn message data in the `input` folder. Each CSV file should have a `CONTENT` column where messages are stored.
2. **URL Extraction**: URLs are extracted from the `CONTENT` column of the CSV file.
3. **URL Analysis**: The extracted URLs are analyzed for phishing risks or any other defined criteria using the `url_analyser` module.
4. **Results Saving**: The analyzed URLs are saved in an Excel file located in the `output` folder with the format `filename_url_analysis_results.xlsx` (where `filename` is the input CSV files name without `.csv`).
5. **Loading Animation**: While extracting and analyzing URLs, a rotating loader appears in the terminal, indicating progress.
6. **Processed Files Logging**: Once a CSV file has been processed, its filename is logged in `processed_files.log` to prevent duplicate processing.

## Prerequisites

Make sure to install the following dependencies before running the project:

- **Python 3.x**
- **Pandas**: For handling CSV files and data frames.
- **Requests**: For checking the internet connection.
- **OpenPyXL**: For writing Excel files.

Install the required Python packages using the command:

```bash
python -m venv .venv

.venv\Scripts\activate

pip install -r requirements.txt
```
## usage
```bash
python app.py
```
