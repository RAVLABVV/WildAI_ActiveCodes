Expanded Animal Data Analysis (JupyterNotebook_ExpandedAnimalDataV03.ipynb)
Overview
This Jupyter Notebook processes species observation data and watershed land use maps to generate conductivity maps for ecological analysis. It focuses on integrating geospatial data from multiple watersheds, handling overlapping bounding boxes, and **visualizing species connectivity across the São Lourenço region from 1985 to 2023.**
Prerequisites

Python: 3.8 or higher
Libraries:os
pandas
rasterio
numpy
matplotlib
collections
shapely

Data:
Watershed land use maps (GeoTIFFs) in /home/ravl/.maps/Landuse/Watersheds
Species observation CSVs in /home/ravl/.csvs/inaturalist
Class mapping CSV: /home/ravl/.maps/Landuse/Watersheds/S.Lourenco/MPB_SAO_LOURENCO.csv

Celles: 

Block 0: Imports libraries and sets directories.
Block 1: Composites watershed maps, fixing overlapping bounding boxes for 1985–2023.
Block 2: Updates the watershed directory.
Block 3: Prints spatial extents and visualizes a sample map.
Block 4: Generates and visualizes conductivity maps for species and combined data.

Outputs

Conductivity Maps: GeoTIFFs (*_conductivity.tif) for each species and a combined map.
Visualizations: PNG files (*_conductivity.png) showing normalized probability distributions.
Console Output: Spatial extents and processing logs.

Notes

The notebook assumes consistent GeoTIFF and CSV formats.
Adjust directory paths in Block 0 if your data is stored elsewhere.
Visualizations use a custom black-red-yellow-green colormap.

=======================================================================================================================

Area Trend Generation with ARIMA (JupyterNotebook_AreaTrendGen_1304_WithClamping.ipynb)
Overview
This Jupyter Notebook uses ARIMA models to analyze and forecast land use trends in the São Lourenço region from 1985 to 2033. It processes land use data, evaluates model performance, and generates visualizations of area trends for different land use classes.
Prerequisites

Python: 3.12.8
Libraries:numpy==1.26.4
pandas
pmdarima==2.0.4
sklearn
matplotlib


Data:
Land use CSV: C:\Users\RaulA\OneDrive\Documents\IAAC\Thesis - Digital Urban Landscapes\Maps\MapBiomas\Landuse\S.Lourenco\MPB_SAO_LOURENCO.csv


Usage

Place the input CSV in the specified path.
Open the notebook:jupyter notebook JupyterNotebook_AreaTrendGen_1304_WithClamping.ipynb


Cells:
Cell 1: Imports libraries and checks versions.
Cell 2: Loads and preprocesses land use data, creating pivot and proportion tables.
Cell 3: Prints data paths for verification.
Cell 4: Displays data structure and preview.
Cell 5: Fits ARIMA models, evaluates on 2016–2023, and forecasts 2024–2033.
Cell 6: Generates line graphs for each land use class.


Outputs
CSV Files:
landuse_pivot.csv: Pivoted land use data.
arima_forecast_final_retrained.csv: Forecasted areas for 1985–2033.


Visualizations: Line graphs for each land use class, showing historical (1985–2023) and forecasted (2024–2033) areas.
Console Output: Model evaluation metrics (MSE), data previews, and processing logs.


Notes
The notebook uses a dark background for visualizations; adjust plt.style if needed.
ARIMA models are retrained on full data for final forecasts.
Ensure the input CSV path is correct for your system.

=======================================================================================================================

AI-Based Spatial Ecological Modeling (JupyterNotebook_AI_SEM_120525.ipynb)
*Help Needed the Most*

Overview
This Jupyter Notebook performs spatial ecological modeling using AI techniques (Random Forest, XGBoost, ARIMA) to analyze land use changes in the São Lourenço region. It processes GeoTIFFs and CSV data, computes neighborhood statistics, and visualizes land use class proportions from 1985 to 2023, with GPU acceleration support.
Prerequisites

Python: 3.13.0
Libraries:os
glob
rasterio
cupy==13.0.0
numpy==1.26.4
pandas
xgboost
statsmodels
scikit-learn
matplotlib
seaborn
h5py

Install via:pip install rasterio cupy numpy pandas xgboost statsmodels scikit-learn matplotlib seaborn h5py


Hardware: NVIDIA GPU with CUDA support (optional for GPU acceleration).
Data:
GeoTIFFs: /home/ravl/.maps/Landuse/Watersheds/S.Lourenco/DATA/Scaled/*.tif
CSV: /home/ravl/.maps/Landuse/Watersheds/S.Lourenco/MPB_SAO_LOURENCO.csv

Outputs

Visualizations: Plot of land use class proportions over time (1985–2023).
Console Output: GPU configuration, data validation logs, and class proportion details.
Predicted Maps: GeoTIFFs in the output directory (if forecasting is enabled).

Notes

GPU acceleration requires a compatible NVIDIA GPU and CUDA setup.
The notebook includes error handling for missing data files.
Adjust paths in Cell 2 if your data is stored differently.


=======================================================================================================================

Heatmap and Tension Map Generation (JupyterNotebook_HEATMAPTENSIONMAP.ipynb)

Overview
This Jupyter Notebook generates heatmaps and tension maps to analyze land use/land cover (LULC) changes in the São Lourenço region from 1985 to 2023. It processes GeoTIFFs, identifies transitions between land use classes, and visualizes spatial and numerical change patterns.
Prerequisites

Python: 3.13.0
Libraries:os
numpy
pandas
rasterio
matplotlib
sklearn
IPython

Install via:pip install numpy pandas rasterio matplotlib scikit-learn ipython


Data:
LULC GeoTIFFs: C:\Users\RaulA\OneDrive\Documents\IAAC\Thesis - Digital Urban Landscapes\Maps\MapBiomas\Landuse\S.Lourenco\DATA\Scaled\*.tif
Class CSV: C:\Users\RaulA\OneDrive\Documents\IAAC\Thesis - Digital Urban Landscapes\Maps\MapBiomas\Landuse\S.Lourenco\MPB_SAO_LOURENCO.csv


Usage
Ensure GeoTIFFs and CSV are in the specified paths.
Open the notebook:jupyter notebook JupyterNotebook_HEATMAPTENSIONMAP.ipynb


Cells:
Cell 1: Imports libraries and sets input/output paths.
Cell 2: Loads class definitions from CSV.
Cell 3: Loads LULC GeoTIFFs.
Cell 4: Defines transitions using a predefined matrix.
Cell 5: Generates heatmaps for yearly LULC changes.
Cell 6: Visualizes heatmaps and clusters changes.
Cell 7: Integrates numerical and spatial results (centroid, directionality).


Outputs

Heatmaps: GeoTIFFs (yearly_heatmap_YYYY_to_YYYY.tif) showing LULC change intensity.
Visualizations: Plots of change intensity and clusters for each year pair.
Console Output: Total change intensity, centroids, and directionality slopes for each heatmap.


=======================================================================================================================



License
This project is licensed under the MIT License.
Contact
For issues or questions, contact [raul.alexandre.bertagnoli@students.iaac.net] or open an issue on GitHub.


