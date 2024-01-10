# ML
This project showcases the use of `Python` and `Jupyterlab` for machine learning projects. 
Directory structure below contains example files/directries like fnn, lightgbm and so on.

## Directory structure
---
.<br>
├── Dockerfile<br>
├── LICENSE<br>
├── Makefile<br>
├── README.md<br>
├── clean-layer.sh<br>
├── data<br>
│   ├── external<br>
│   ├── intrim<br>
│   ├── processed<br>
│   └── raw<br>
├── docker-compose.yml<br>
├── docs<br>
├── models<br>
├── notebooks<br>
├── references<br>
├── reports<br>
│   └── figures<br>
├── requirements_conda.txt<br>
├── requirements_pip.txt<br>
├── setup.py<br>
├── src<br>
│   ├── __init__.py<br>
│   ├── data<br>
│   │   └── make_dataset.py<br>
│   ├── models<br>
│   │   ├── base<br>
│   │   │   ├── __init__.py<br>
│   │   │   ├── model.py<br>
│   │   │   └── preprocess.py<br>
│   │   ├── fnn<br>
│   │   │   ├── __init__.py<br>
│   │   │   ├── model.py<br>
│   │   │   └── preprocess.py<br>
│   │   └── lightgbm<br>
│   │       ├── __init__.py<br>
│   │       ├── model.py<br>
│   │       └── preprocess.py<br>
│   ├── train.py<br>
│   └── visualization<br>
│       └── visualize.py<br>
└── tox.ini<br>

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
