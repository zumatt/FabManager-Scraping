# FabManager-Scraping

[![Build and Deploy](https://github.com/zumatt/FabManager-Scraping/actions/workflows/deploy.yml/badge.svg)](https://github.com/zumatt/FabManager-Scraping/actions/workflows/deploy.yml)
[![lite-badge](https://jupyterlite.rtfd.io/en/latest/_static/badge.svg)](https://zumatt.github.io/FabManager-Scraping)

The repo is archived to leave space to a Python package to perform the same actions as the ones included into this notebooks and others including an analysis of the results.
You can check the new repo here: [![View FabManager-Data-Analyzer on GitHub](https://img.shields.io/github/stars/zumatt/FabManager-Data-Analyzer?color=232323&label=FabManager-Data-Analyzer&logo=github&labelColor=232323)](https://github.com/zumatt/FabManager-Data-Analyzer)

A collection of Python notebooks for scraping and exporting data from FabManager instances using the Open API.

## 📋 Overview

This project provides interactive Jupyter notebooks to extract data from FabManager platforms. FabManager is a management system for Fab Labs and makerspaces. These notebooks allow administrators to export user data, machine information, reservations, and training records in JSON format for backup, analysis, or migration purposes.

## 🚀 Quick Start

You can use these notebooks in two ways:

1. **Online (Browser-based)**: Click the JupyterLite badge above to run directly in your browser, be sure to enable CORS headers for the Open API
2. **Local (Python environment)**: Clone this repository and run locally with Jupyter, VS Code or similar

## 📚 Notebooks

### 1. dataScraper_FabManager.ipynb (Browser-based)

**Purpose**: Scrape FabManager data directly from your browser using JupyterLite.

**Best for**:
- Quick data exports without installing Python
- Users who prefer browser-based tools
- Testing the API without local setup

**Requirements**:
- Modern web browser
- No local Python installation needed
- **Important**: Your FabManager server must have CORS enabled for the Open API

**How to use**:
1. Open the notebook in [JupyterLite](https://zumatt.github.io/FabManager-Scraping)
2. Configure your FabManager URL and API token in the configuration cell
3. Run the test connection cell to verify access
4. Choose a data type (users, machines, reservations, or trainings)
5. Run the scraping cells to export data
6. Download the generated JSON files from the exports folder

**Known limitations**:
- Requires CORS to be enabled on your FabManager server
- Large datasets may be slower than local execution
- Downloads are handled through browser

### 2. dataScraper_Local_FabManager.ipynb (Local/Offline)

**Purpose**: Scrape FabManager data from a local Python environment.

**Best for**:
- Regular/automated data exports
- Large datasets
- Production use without CORS restrictions
- Integration with existing Python workflows

**Requirements**:
- Python 3.11 or higher
- Dependencies from `requirements.txt`
- Jupyter Lab, Jupyter Notebook, or VS Code with Jupyter extension

**How to use**:
1. Clone this repository:
   ```bash
   git clone https://github.com/zumatt/FabManager-Scraping.git
   cd FabManager-Scraping
   ```

2. Create and activate a virtual environment (recommended):
   ```bash
   # Create virtual environment
   python3 -m venv venv
   
   # Activate it (macOS/Linux)
   source venv/bin/activate
   
   # Or on Windows
   # venv\Scripts\activate
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Open the notebook in VS Code (tested) or preferred method.

5. Configure your FabManager URL and API token in the configuration cell
6. Run the test connection cell to verify access
7. Choose a data type and run the scraping cells
8. Find exported JSON files in the `content/exports/` directory

**Advantages over browser version**:
- No CORS restrictions
- Better performance for large datasets
- Can be automated or scheduled
- More reliable for production use

## 🔧 Configuration

Both notebooks require two configuration parameters:

- **BASE_URL**: Your FabManager instance URL (e.g., `https://fabmanager.example.com`)
- **API_TOKEN**: Your FabManager Open API token

To get an API token:
1. Log in to your FabManager instance as an administrator
2. Go to Settings → API Access
3. Generate a new API token with appropriate permissions

## 📊 Supported Data Types

Both notebooks can export the following data:

| Data Type | Description | Endpoint |
|-----------|-------------|----------|
| **Users** | All user accounts in the system | `/open_api/v1/users` |
| **Machines** | All available machines/equipment | `/open_api/v1/machines` |
| **Reservations** | All bookings (auto-categorized by type) | `/open_api/v1/reservations` |
| **Trainings** | All training sessions | `/open_api/v1/trainings` |

## ✨ Features

- ✅ Automatic pagination handling (RFC-5988 compliant)
- ✅ Connection testing before data scraping
- ✅ Timestamped output files
- ✅ Clean JSON export (removes unusual line terminators)
- ✅ Progress logging
- ✅ Error handling and reporting
- ✅ Automatic reservation categorization (Machine, Training, Event)

## 📁 Output Format

Exported files are saved in the `content/exports/` directory with the following naming convention:

```
FabManager_ExportedData_{DataType}_{DD_MM_YYYY_HH-MM}.json
```

## ⚠️ Troubleshooting

### CORS Errors (Browser version only)

If you encounter "Failed to fetch" or CORS errors with `dataScraper_FabManager.ipynb`:

1. **Solution 1**: Switch to `dataScraper_Local_FabManager.ipynb` (recommended for production)
2. **Solution 2**: Ask your FabManager admin to enable CORS for the Open API
3. **Solution 3**: Set up a CORS proxy

### Authentication Errors

- Verify your API token is valid and has not expired
- Ensure your user account has appropriate permissions
- Check that the BASE_URL is correct (include `https://` and no trailing slash)

### Connection Timeouts

- Check your network connection
- Verify the FabManager server is accessible
- Try increasing timeout values in the code if needed

