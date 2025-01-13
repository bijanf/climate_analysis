# Climate Analysis Package

## Overview
The Climate Analysis Package is a powerful tool designed for analyzing climate data with a focus on generating **time-series visualizations** and **map-based insights**. This package supports processing CMIP6 data, calculating regional means, and visualizing climate anomalies, making it ideal for climate scientists, researchers, and data analysts.

## Features
- **Time-Series Analysis**: Generate detailed time-series plots of temperature or other variables over time for specified experiments.
- **Map Visualizations**: Create spatial maps of climate variables, regridded to a specified resolution.
- **Customizable**: Set your own region of interest, experiments, and climatological baselines.
- **Automated Processing**: Handles CMIP6 datasets, including preprocessing and anomaly computation.

## Installation
1. Clone the repository:
   ```bash
   git clone <repository_url>
   ```

2. Navigate to the package directory:
   ```bash
   cd climate_analysis_package
   ```

3. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Install the package:
   ```bash
   python setup.py install
   ```

## Usage
The package provides two main functionalities: **time-series plots** and **map-based visualizations**.

### Time-Series Plots
Generate time-series plots to visualize climate variable anomalies over time.

#### Command
```bash
generate-time-series \
    --catalog_url https://storage.googleapis.com/cmip6/pangeo-cmip6.json \
    --experiments historical ssp585 \
    --lat_range 35 57 \
    --lon_range 45 88 \
    --climatology_start 1981 \
    --climatology_end 2010 \
    --output time_series_output.png \
    --variable tas
```

#### Example
```bash
generate-time-series \
    --catalog_url https://storage.googleapis.com/cmip6/pangeo-cmip6.json \
    --experiments historical ssp126 ssp245 ssp370 ssp585 \
    --lat_range 30 60 \
    --lon_range 30 90 \
    --climatology_start 1981 \
    --climatology_end 2010 \
    --output time_series_plot.png \
    --variable tas
```

#### Output
- **Plot**: Saved as `time_series_output.png`.
- **Model List**: A text file `time_series_output_models.txt` containing all models used for the plot.

### Map Visualizations
Generate map visualizations of regridded climate variable differences between scenarios.

#### Command
```bash
generate-maps \
    --catalog_url https://storage.googleapis.com/cmip6/pangeo-cmip6.json \
    --experiments ssp126 \
    --lat_range 35 57 \
    --lon_range 45 88 \
    --output map_output.png
```

#### Example
```bash
generate-maps \
    --catalog_url https://storage.googleapis.com/cmip6/pangeo-cmip6.json \
    --experiments historical ssp585 \
    --lat_range 35 57 \
    --lon_range 45 87 \
    --output climate_map.png
```

#### Output
- **Map**: Saved as `map_output.png`.

## Contributing
We welcome contributions to the Climate Analysis Package! To contribute:

1. **Fork the Repository**:
   - Visit the GitHub repository and fork it to your account.

2. **Clone Your Fork**:
   ```bash
   git clone <your_fork_url>
   ```

3. **Create a New Branch**:
   ```bash
   git checkout -b feature/your-feature-name
   ```

4. **Make Changes**:
   - Edit the code, add new features, or fix bugs.
   - Follow the existing code style and conventions.

5. **Test Your Changes**:
   - Ensure all tests pass by running NOT implemented yet :
     ```bash
     pytest
     ```
   - Add new tests if needed.

6. **Commit Your Changes**:
   ```bash
   git add .
   git commit -m "Add your descriptive commit message"
   ```

7. **Push Your Changes**:
   ```bash
   git push origin feature/your-feature-name
   ```

8. **Create a Pull Request**:
   - Go to the original repository and create a pull request from your branch.

### Guidelines
- **Code Style**: Follow PEP 8 standards for Python code.
- **Documentation**: Update the README.md or docstrings as needed.
- **Tests**: Ensure new features or changes are covered by tests.

## Key Parameters
- **`catalog_url`**: URL to the CMIP6 data catalog (e.g., `https://storage.googleapis.com/cmip6/pangeo-cmip6.json`).
- **`experiments`**: List of experiments to include (e.g., `historical`, `ssp585`).
- **`lat_range`** and **`lon_range`**: Latitude and longitude bounds for the region of interest.
- **`variable`**: Climate variable to analyze (e.g., `tas`, `pr`).
- **`climatology_start`** and **`climatology_end`**: Years for the climatology baseline.
- **`target_resolution`**: Spatial resolution for regridding (in degrees).

## Keywords
- Climate Analysis
- CMIP6
- Regional Climate
- Climate Modeling
- Climate Visualization
- Time-Series Analysis
- Map Visualization

## License
This package is licensed under the MIT License. See the `LICENSE` file for details.

## Author
**Bijan Fallah**  
Climate Scientist, Berlin  
[Linkedin](https://www.linkedin.com/in/bijanfallah/)

