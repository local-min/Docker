# ML
This project showcases the use of `Python` and `Jupyterlab` for machine learning projects. 
Directory structure below contains example files/directries like fnn, lightgbm and so on.

## Directory structure
---
```
.
├── Dockerfile
├── LICENSE
├── Makefile
├── README.md
├── clean-layer.sh
├── data
│   ├── external
│   ├── intrim
│   ├── processed
│   └── raw
├── docker-compose.yml
├── docs
├── models
├── notebooks
├── references
├── reports
│   └── figures
├── requirements_conda.txt
├── requirements_pip.txt
├── setup.py
├── src
│   ├── __init__.py
│   ├── data
│   │   └── make_dataset.py
│   ├── models
│   │   ├── base
│   │   │   ├── __init__.py
│   │   │   ├── model.py
│   │   │   └── preprocess.py
│   │   ├── fnn
│   │   │   ├── __init__.py
│   │   │   ├── model.py
│   │   │   └── preprocess.py
│   │   └── lightgbm
│   │       ├── __init__.py
│   │       ├── model.py
│   │       └── preprocess.py
│   ├── train.py
│   └── visualization
│       └── visualize.py
└── tox.ini
```

## How to use
---
Clone this repo and run the below docker command:

`To Start Application`:
```docker
docker-compose up --build
```
and navigate to http://localhost:8080/ .

`To Stop Application`:
```docker
docker-compose down
```
