FROM --platform=linux/amd64 ubuntu:22.04

ADD clean-layer.sh /tmp/clean-layer.sh
COPY requirements_conda.txt ./
COPY requirements_pip.txt ./

ARG DEBIAN_FRONTEND=noninteractive

# Make sure python version you want to use
ENV PYTHON_MAJOR_VERSION=3
ENV PYTHON_MINOR_VERSION=11
ENV PATH="/root/miniconda3/bin:${PATH}"

# Update and install necessary modules.
RUN apt update && \
    apt install -y git vim wget zip unzip curl make cmake && \
    wget --quiet https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh && \
    mkdir /root/.conda && \
    bash Miniconda3-latest-Linux-x86_64.sh -b && \
    rm -f Miniconda3-latest-Linux-x86_64.sh && \
    chmod +x /tmp/clean-layer.sh && \
    /tmp/clean-layer.sh

# Install python
RUN conda config --add channels conda-forge && \
    conda config --add channels nvidia && \
    conda config --add channels pytorch && \
    conda config --add channels rapidsai && \
    conda install --yes python=$PYTHON_MAJOR_VERSION.$PYTHON_MINOR_VERSION && \
    apt install -y python3-pip && \
    /tmp/clean-layer.sh

# Install conda packages.
# Conda can solve dependency problem, and running speed is fast more than pip packages.
RUN conda install --yes --file requirements_conda.txt && \
    /tmp/clean-layer.sh

# Install pip packages. The packages, libsm6 libxrender1 are needed for opencv.
RUN apt install -y libsm6 libxrender1 --fix-missing && \
    pip3 install --no-cache-dir -r requirements_pip.txt && \
    /tmp/clean-layer.sh

# Install MeCab and NEologd dic (Japanese useful dictionary)
# RUN apt install -y sudo mecab mecab-ipadic libmecab-dev && \
#     git clone --depth 1 https://github.com/neologd/mecab-ipadic-neologd.git && \
#     chmod 777 ./mecab-ipadic-neologd/bin/install-mecab-ipadic-neologd && \
#     ./mecab-ipadic-neologd/bin/install-mecab-ipadic-neologd -y -n && \
#     cp /etc/mecabrc /usr/local/etc/mecabrc && \
#     /tmp/clean-layer.sh

# Install jupyterlab and jupyter-kite (https://github.com/kiteco/jupyterlab-kite)
RUN pip3 install --upgrade --no-cache-dir 'jupyterlab~=4.0' jupyterlab-git && \
    pip3 install jupyterlab-language-pack-ja-JP && \
    # curl -sL https://deb.nodesource.com/setup_12.x |bash - && \
    # apt install -y --no-install-recommends nodejs && \
    # wget --quiet https://linux.kite.com/dls/linux/current && \
    # pip3 install --upgrade --no-cache-dir  jupyter-kite && \
    # jupyter labextension install "@kiteco/jupyterlab-kite" && \
    /tmp/clean-layer.sh
