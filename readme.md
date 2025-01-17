# Test environments for geopandas

To develop geopandas, sometimes one needs to have a test environment with a certain version of python/  pandas
in order to reproduce a bug report / failure on CI.

This repo contains my latest method of managing these environments, and also serves as a bit of a learning playground with pixi.

##Environments
Environments are declared by the environments table in pixi.toml

To finish initialising an environment, need to run `pixi run --environment <env_name> setup_geopandas`
to install geopandas from source. For the pandas dev environment, need to run `pixi run --environment pandas-dev setup_pandas` first.

## Hard coded configuration
`setup_pandas` and `setup_geopandas` both contain hard coded local paths to where the source distributions live on my machine.


## Start a repl
pixi run --environment pd20 python

pixi run --environment pd22 python



