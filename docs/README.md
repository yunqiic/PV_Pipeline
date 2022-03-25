```shell
sudo docker run -ti --volume="$(pwd)":/DeepSolar --rm python:3.9 bash
sudo docker run -ti --volume="$(pwd)":/DeepSolar --rm python:3.8 bash

# conda
pip install -r requirements.txt -i https://pypi.douban.com/simple
```