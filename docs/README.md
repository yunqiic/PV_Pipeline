```shell
sudo docker run -ti --volume="$(pwd)":/DeepSolar --rm python:3.9 bash
sudo docker run -ti --volume="$(pwd)":/DeepSolar --rm python:3.8 bash

sudo docker run -it --name="anaconda" -p 8888:8888 continuumio/anaconda3 /bin/bash
sudo docker run -it --name="anaconda" --volume="$(pwd)":/DeepSolar --rm -p 8888:8888 continuumio/anaconda3 /bin/bash

conda install -c conda-forge jupyterlab
cd ~
jupyter lab --ip='*' --port=8888 --no-browser --allow-root
docker start anaconda
docker exec -it anaconda /bin/bash
docker rm anaconda
docker image ls

docker run -it --name="anaconda_2" -p 8888:8888 -v `pwd`:/root continuumio/anaconda3 /bin/bash

pip freeze > requirements.txt
pip install -r requirements.txt
 
conda install --file requirements.txt
conda install --yes --file requirements.txt

while read requirement; do conda install --yes $requirement; done < requirements.txt
while read requirement; do conda install --yes $requirement || pip install $requirement; done < requirements.txt

conda env export > freeze.yml
conda env create -f freeze.yml

# conda anaconda
pip install -r requirements.txt -i https://pypi.douban.com/simple
docker search anaconda
docker search conda

# https://mirrors.aliyun.com/anaconda/
# https://mirrors.aliyun.com/anaconda/miniconda/
```

```shell
# 头一次用
docker run -it --name="anaconda" -p 8888:8888 continuumio/anaconda3 /bin/bash
conda install -c conda-forge jupyterlab
cd ~
jupyter lab --ip='*' --port=8888 --no-browser --allow-root

# 用完以后
# Ctrl+C退出jupyter
exit

# 以后再用
docker start anaconda
docker exec -it anaconda /bin/bash
cd ~
jupyter lab --ip='*' --port=8888 --no-browser --allow-root

# 不想要了
docker rm anaconda
```

```
docker anaconda
```

```
docker search anaconda
NAME                                     DESCRIPTION                                     STARS     OFFICIAL   AUTOMATED
continuumio/anaconda3                    Powerful and flexible python distribution       596                  [OK]
continuumio/anaconda                     Powerful and flexible python distribution       219                  [OK]
okwrtdsh/anaconda3                       Anaconda3, Jupyter Notebook, OpenCV3, Tensor…   37                   [OK]
drunkar/anaconda-tensorflow-gpu          anaconda-tensorflow-gpu                         12                   [OK]
continuumio/anaconda2                                                                    4
fzinfz/anaconda3                         multi-kernel jupyter(py 3.7+/2.7.15 & bash) …   4
marketdial/anaconda3-uwsgi-nginx-flask   A custimized image based on anaconda3 with u…   2
continuumio/anaconda-pkg-build                                                           1
geordgez/anaconda-sh                                                                     1
kunitaya/anaconda3                       Anaconda3 on CentOS                             1                    [OK]
xychelsea/anaconda3                      Anaconda 3 base containers, including with N…   1
mikewright/anaconda-tensorflow           An image that can be used to quickly start a…   1                    [OK]
orianna/anaconda                         Docker image with Anaconda and Jupyter Noteb…   1
quantrocket/anaconda3-uwsgi              Learn more at https://www.quantrocket.com       1                    [OK]
ssusb/anaconda3                                                                          0
weekswp/anaconda                                                                         0
purposefly/anaconda                      Python 3.6 + Anaconda 3                         0                    [OK]
shotat/anaconda3-xgboost-docker          anaconda3 & xgboost                             0                    [OK]
pnnlmiscscripts/anaconda                                                                 0
kobanerjee/anaconda                                                                      0
rndnet/anaconda-bfj                      RnDnet platform execution container. Use con…   0
pickledfish/anaconda_dreams                                                              0
continuumio/anaconda-build-linux-32                                                      0
continuumio/anaconda-build-linux-64                                                      0
xuhui546/anaconda-centos                 A Dockerfile that produces a Docker Image fo…   0                    [OK]

docker search conda
NAME                                      DESCRIPTION                                     STARS     OFFICIAL   AUTOMATED
conda/miniconda3                          Ready to use, debian-based, miniconda3 docke…   44                   [OK]
conda/miniconda3-centos7                  Miniconda3, CentOS7                             9                    [OK]
condaforge/miniforge3                     Container image that includes conda-forge's …   9
condaforge/mambaforge                     Container image that includes conda-forge's …   9
condaforge/linux-anvil                    The image used to build x86_64 conda distrib…   7                    [OK]
continuumio/conda-ci-linux-64-python3.8                                                   6
continuumio/conda_builder_linux           A build platform for Linux packages (64-bit …   4
conda/concourse-rsync-resource            A concourse resource for shuttling intermedi…   4
conda/c3i-linux-64                                                                        4
continuumio/conda-ci-linux-64-python3.7                                                   3
conda/miniconda2                          Ready to use, debian-based, miniconda2 docke…   2                    [OK]
condaforge/linux-anvil-cuda                                                               2
continuumio/conda-ci-linux-64-python3.9                                                   1
condaforge/linux-anvil-ppc64le                                                            1
condaforge/linux-anvil-aarch64                                                            1
condaforge/linux-anvil-comp7                                                              1
condaforge/mambaforge-pypy3               Container image that includes conda-forge's …   1
continuumio/conda-concourse-ci            Build and general-purpose image for Continuu…   0
continuumio/conda-ci-linux-64-python2.7                                                   0
condaforge/rego-cf-autotick-bot-action    regro-cf-autotick-bot GitHub Action             0
condaforge/automerge-action                                                               0
condaforge/webservices-dispatch-action                                                    0
condatest/repo_cli                                                                        0
ibmcom/conda-verify                                                                       0
ibmcom/conda-verify-ppc64le               Docker image for conda-verify-ppc64le           0
```