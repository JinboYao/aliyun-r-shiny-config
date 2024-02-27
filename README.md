# Aliyun R Shiny Configuration

This repository contains configuration files for running an R Shiny web application on Aliyun. The provided configuration is designed to set up the necessary dependencies and configurations to deploy the Shiny app on an Aliyun server.

## Configuration Files

- **aliyun_config.sh**: Shell script for configuring R and Shiny Server on Aliyun.

## Usage
### Requirement

#### R Installation Dependencies 

Before installing the R packages, ensure the necessary dependencies are installed by running the following commands: 

```sh
sudo apt-get install libfontconfig1-dev libfreetype6-dev
sudo apt-get install libcurl4-openssl-dev
sudo apt-get install libxml2-dev
sudo apt-get install libfreetype6-dev libpng-dev libtiff5-dev libjpeg-dev
```

#### R Installation Dependencies 

Before installing the R packages, ensure the necessary dependencies are installed by running the following commands: 

```
install.packages("shiny")
install.packages("ggplot2")
install.packages(c("usethis", "pkgdown", "rcmdcheck", "roxygen2", "rversions", "urlchecker"))
install.packages("ragg")
install.packages("prettyGraphs")
install.packages("shinydashboard")
install.packages("DT")
install.packages("markdown")
install.packages("devtools")

library(devtools)
devtools::install("/home/jinbo/samplyzer")
library(samplyzer)
```



#### Aliyun configuration

Make sure to update and install the necessary components for R and Shiny Server on Aliyun using the following commands:

```sh
sudo apt-get update
sudo apt-get install r-base r-base-dev
sudo apt-get install gdebi-core
wget https://download3.rstudio.org/ubuntu-14.04/x86_64/shiny-server-1.5.16.958-amd64.deb
sudo gdebi shiny-server-1.5.16.958-amd64.deb
sudo ln -s /home/jinbo/samplyzer/inst/apps/samplyzer /srv/shiny-server/samplyzer
```

### Run

To run the Shiny app, execute the following commands:

```sh
library(shiny)
library(ggplot2)
runApp('/home/jinbo/samplyzer/inst/apps/samplyzer')
```

**shiny-server**

After making changes or updates, restart the Shiny Server using:

```sh
sudo systemctl restart shiny-server
```

## Contributing

Feel free to contribute by opening issues or creating pull requests.
