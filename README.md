# UAS Risk Analysis Project

This project aims to analyze the risk associated with Unmanned Aircraft System (UAS) sightings and flight data, leveraging data curation, exploratory data analysis (EDA), and potentially machine learning techniques.

## Project Structure

The project is organized into the following main directories:

*   **`data_analysis`**: Contains notebooks for exploratory data analysis using PySpark.
*   **`data_curation`**: Includes notebooks and scripts for data collection, cleaning, and preparation.
*   **`mockups`**: Contains diagrams and images related to the project's data stack and visualizations.
*   **`open_sky_api_demo`**: Demonstrates the use of the OpenSky Network API.
*   **`pyopensky-demo`**: A demo notebook for interacting with the pyopensky library.
*   **`src`**: Contains source code for reusable modules and packages.

## Key Components

### 1. Data Curation (`data_curation`)

The `data_curation` directory focuses on gathering and preparing the data for analysis.

*   **[`curate_datasets.ipynb`](data_curation/curate_datasets.ipynb)**:  This notebook is responsible for the ETL process of combining and cleaning the various UAS sightings datasets.

*   **`datasets`**:  This directory contains the raw and processed datasets used in the analysis.
    *   **`airports`**: Contains airport data in CSV and JSON formats.
    *   **`uas_sightings_reports`**:
        *   **`raw`**:  Contains the original UAS sightings reports in various Excel formats (XLSX, XLS).  These are the source files that `curate_datasets.ipynb` processes.
        *   **`zero_shot`**: Contains processed UAS sightings data in CSV and Parquet formats, likely the output of the curation process.
    *   **`uasfm_grids`**: Contains data related to FAA UAS Facility Maps.  The ZIP file likely contains geospatial data.

*   **`get_flight_data`**: This folder will contain all logic for getting flight data, and has the python script [get_flight_data.py](data_curation/get_flight_data/get_flight_data.py) for retrieving flight data, and has the default environment variables [default.env](data_curation/get_flight_data/default.env) for the python script.

### 2. Data Analysis (`data_analysis`)

The `data_analysis` directory contains notebooks for exploring and visualizing the UAS sightings data using PySpark.

*   **[`uas_risk_analysis_pyspark_eda.ipynb`](data_analysis/uas_risk_analysis_pyspark_eda.ipynb)**:  This is the main notebook for exploratory data analysis, providing insights into the UAS risk.
*   **[`uas_risk_analysis_viz.ipynb`](data_analysis/uas_risk_analysis_viz.ipynb)**:  This notebook focuses on creating visualizations to communicate the findings of the analysis.
*   **`data_analysis_aws_glue_pyspark_example.ipynb`**: Example of running data analysis with AWS Glue and PySpark.
*   **`data_analysis_local_pyspark_example.ipynb`**: Example of running data analysis locally with PySpark.

### 3. Source Code (`src`)

The `src` directory contains reusable Python packages for the project.

*   **`uas_risk_analysis_packages`**:
    *   **`eda.py`**:  Likely contains functions related to exploratory data analysis.
    *   **`ml`**:
        *   **`functions.py`**: Contains machine learning related functions

### 4. Mockups (`mockups`)

The `mockups` directory contains diagrams and images.

*   **`data_stack_diagram.drawio` / `data_stack_diagram.png` / `data_stack_diagram_final.png`**: Data stack diagrams illustrating the architecture of the project.
*   **`res`**: Contains images, likely used in reports or documentation.

## Dependencies

The project's dependencies are listed in the `requirements.txt` files located in the root directory and the `data_curation` directory.  You can install them using pip:

```shell
python -m pip install -e .
```


## Usage

1.  **Data Curation:** Run the [`curate_datasets.ipynb`](data_curation/curate_datasets.ipynb) notebook to process the raw UAS sightings data and generate the processed datasets.
2.  **Exploratory Data Analysis:** Use the [`uas_risk_analysis_pyspark_eda.ipynb`](data_analysis/uas_risk_analysis_pyspark_eda.ipynb) notebook to explore the data and identify potential risk factors.
3.  **Visualization:**  Utilize the [`uas_risk_analysis_viz.ipynb`](data_analysis/uas_risk_analysis_viz.ipynb) notebook to create visualizations of the data.

## License

This project is licensed under the MIT License - see the [`LICENSE`](LICENSE) file in the root directory for details.
