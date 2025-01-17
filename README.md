<!-- badges: start -->
[![R-CMD-check](https://github.com/AgrDataSci/ag5Tools/workflows/R-CMD-check/badge.svg)](https://github.com/AgrDataSci/ag5Tools/actions)
[![CRAN](https://www.r-pkg.org/badges/version/ag5Tools)](https://cran.r-project.org/package=ag5Tools)
[![Downloads](https://cranlogs.r-pkg.org/badges/grand-total/ag5Tools)](https://cran.r-project.org/package=ag5Tools)
[![Contributor Covenant](https://img.shields.io/badge/Contributor%20Covenant-2.1-4baaaa.svg)](https://agrdatasci.github.io/ag5Tools/CODE_OF_CONDUCT.html)
 <!-- badges: end -->

# ag5Tools

## Toolbox for downloading and extracting data from the Copernicus AgERA5 dataset

## Description

The R package *ag5Tools* is a toolbox to download and extract data from the "Agrometeorological indicators from 1979 to present derived from reanalysis" dataset (AgERA5).

A description of the dataset can found [here](https://cds.climate.copernicus.eu/datasets/sis-agrometeorological-indicators?tab=overview)

The download function provides programmatic access to the Copernicus Climate Data Store to download AgERA5 data.

A detailed description of the ag5Tools package can be found in the companion paper: https://doi.org/10.1016/j.softx.2022.101267

## Data license

The *ag5Tools* package does not distribute data, it only provides access to the Climate Data Store through the Python cdsapi.

For specific details about the license agreement on downloading and using Copernicus Products, please check the license [here](https://cds.climate.copernicus.eu/datasets/sis-agrometeorological-indicators?tab=overview)

### Installation
The stable version of *ag5Tools* can be installed from **CRAN** using 
```r
install.packages("ag5Tools")
```  
The development version could be installed using
``` r
devtools::install_github("agrdatasci/ag5Tools", build_vignettes = TRUE)
```

### Downloading AgERA5 data

#### Install Python and the CDS API
Before using the *ag5Tools* package, you need to intall Python and the CDS API, please see the detailsin the [CDSAPI guide](https://cds.climate.copernicus.eu/how-to-api)

#### Get your CDS API-Key

To download AgERA5 data you should first register at the Climate Data Store and get your API key. Please follow the instructions detailed in the [CDSAPI guide](https://cds.climate.copernicus.eu/how-to-api)

You need to create a file to store the API key. Please follow the instructions detailed [here](https://cds.climate.copernicus.eu/how-to-api)

#### Examples

#### Downloading data

The following example downloads daily '2m_temperature' data for year 2015

``` r
ag5_download(variable = "2m_temperature",
             statistic = "night_time_minimum",
             day = "all",
             month = "all",
             year = 2015,
             path = "C:/custom_target_folder"
             )
```

#### Extracting data

To extract maximum day temperature ("Max-Day-Time") of "2m_temperature"

``` r
ag5_extract(coords = c(35.726364, -2.197162), 
            dates = "1995-01-23", 
            variable = "2m_temperature",
            statistic = "Max-Day-Time", 
            path = "C:/agera5_data")
```

## Acknowledgements

The *ag5Tools* package relies on the functionality available from other open source packages.

-   The Python [*cdsapi*](https://pypi.org/project/cdsapi/)

-   The R package [*reticulate*](https://cran.r-project.org/package=reticulate) is used to access the Python CDS API functions from R.

-   The R package [*terra*](https://cran.r-project.org/package=terra) is used to extract data from nc files.

-   The R package [*fs*](https://cran.r-project.org/package=fs) is used for efficiently search and list files.

## License

Please be aware that *ag5Tools* is released under MIT license, please find details in the [MIT license document](https://agrdatasci.github.io/ag5Tools/LICENSE.html)

## Citation
To cite the *ag5Tools* in scientific publications please use:  

Brown, D., de Sousa, K., & van Etten, J. (2023). ag5Tools: An R package for downloading and extracting agrometeorological data from the AgERA5 database. SoftwareX, 21, 101267. https://doi.org/10.1016/j.softx.2022.101267 

## Code of Conduct

Please note that the *ag5Tools* project is released with a [Contributor Code of Conduct](https://agrdatasci.github.io/ag5Tools/CODE_OF_CONDUCT.html). By contributing to this project, you agree to abide by its terms.

