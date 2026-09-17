# UK Wind Power Infrastructure Optimisation

MSci masters project — optimising the siting of offshore wind farms across the UK using
ERA5 reanalysis data and a genetic algorithm over real geographic constraints.

**MSci Physics, University College London (2023)**

![Python](https://img.shields.io/badge/Python-3.x-blue)
![ERA5](https://img.shields.io/badge/data-ERA5%20reanalysis-6699cc)
![Method](https://img.shields.io/badge/method-genetic%20algorithm-orange)
![License](https://img.shields.io/badge/License-MIT-green)

## Overview

Where should the UK put its offshore wind farms? The answer depends on wind resource, water
depth, distance from the coastline, and how farms interfere with one another — a search space
far too large to enumerate.

This project builds the pieces needed to answer it: opening and processing ERA5 GRIB/NetCDF
reanalysis fields, extrapolating wind speed to turbine hub height, converting speed to power
output, constructing a wind farm model, and then optimising site layouts with a genetic
algorithm that scores candidate configurations against a fitness function combining yield,
bathymetry and coastal distance.

## Notebooks

The notebooks are numbered to be read in order — each builds on the previous.

| Notebook | Content |
| --- | --- |
| `Starting to open gribs` | First look at GRIB files — wind speed maps and frequency distributions |
| `0 - Old GRIB Export` | Data retrieval, height extrapolation, wind power output functions |
| `1-Creating Dataset` | Opening NetCDF, grid separation, building the working dataset |
| `2-Analysing` | Statistical analysis, rolling averages over multiple time windows |
| `3-CreatingWindFarmModel` | Wind farm model — siting, turbine counts per grid cell |
| `4-GeneticAlgorithm` | Genetic algorithm with a parallelised fitness function |
| `5-DistancefromCoastline` | Coastline extraction and haversine distance constraints |
| `6-Multipleruns` | Repeated optimisation runs for stability |
| `9-GAWeightingWindfarms` | Weighted multi-farm optimisation — the largest model |
| `10 - Depth` | Bathymetry added to the fitness function |
| `11-TestingGAParameters` | Genetic algorithm parameter sensitivity |

## Data

Wind fields come from the ECMWF **ERA5 reanalysis**, read as GRIB and NetCDF. The datasets
are large and are not committed; the notebooks document retrieval and export.

## Author

Harvey Bermingham — MSci Physics, University College London

## License

Released under the MIT License. See [LICENSE](LICENSE).
