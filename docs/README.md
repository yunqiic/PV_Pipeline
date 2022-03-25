```shell
docker run -ti --volume="$(pwd)":/DeepSolar --rm python:3.9 bash
pip install -r requirements.txt -i https://pypi.douban.com/simple
```