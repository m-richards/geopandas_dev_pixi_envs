# Test environments for geopandas

To develop geopandas, sometimes one needs to have a test environment with a certain version of python/  pandas
in order to reproduce a bug report / failure on CI.

This repo contains my latest method of managing these environments using [pixi](https://github.com/prefix-dev/pixi), and also serves as a bit of a learning playground for the tool.

**I'm not a pixi expert**, things I'm doing here are likely non optimal.

## Layout
Here I assume a structure:
```
geopandas/
├── # This folder corresponds to https://github.com/m-richards/geopandas_dev_pixi_envs
├── .pixi/
├── pixi.lock
├── pixi.toml
├── README.md
└── geopandas_fork/
    ├── # This folder corresponds to https://github.com/m-richards/geopandas
    ├── ci
    ├── doc
    ├── geopandas
    ├── .gitattributes
    ├── .gitignore
    ├── .LICENSE.TXT
    └── README.md
```

## Environments
Environments are declared by the environments table in pixi.toml

To finish initialising an environment, ~~need to run `pixi run --environment <env_name> setup_geopandas`~~
to install geopandas from source. For the pandas dev environment, need to run `pixi run --environment pandas-dev setup_pandas` first.

## Other hard coded configuration
I have an environment building against the main version of pandas as an editiable install. The
`setup_pandas` command contains hard coded local paths to where the repo lives on my machine.


## Start a repl
* `pixi run --environment pd20 python`
* `pixi run --environment pd22 python`

## Build docs

`pixi run docs build_docs`
`pixi run docs clean_docs`

(Note this command is defined such that it uses the docs environment by default)




