## How to embed python3 into golang (MacOS + Docker as an example)

ONLY `Docker` is required for this experiment. Install `Docker` if you haven't install it yet.

## Description

We have two repos

- [python-model](https://github.com/denghejun/python-model) : Hosting the python3 source code.
- [go-app](https://github.com/denghejun/python-in-go): Application based on golang, will interact
  with [python-model](https://github.com/denghejun/python-model)

For this repo, we assume we just need do some changes as usually we do. E.g. we did some changes in
src/package_a/foo.py. After that, we need to build a latest `python-model` image based on new version number:

- `docker build --no-cache --progress=plain -t python-model:v1.0.1 -f docker/python/Dockerfile .`
