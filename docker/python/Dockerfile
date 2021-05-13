# **********************
# docker build --no-cache --progress=plain -t python-model:v1.0.1 -f docker/python/Dockerfile .
# **********************
FROM python:3.7-slim-buster
ENV SRC=./src/
ENV WORKDIR=/build/
COPY ${SRC} ${WORKDIR}
WORKDIR ${WORKDIR}
RUN python3 setup.py sdist --formats=gztar -d __dist__
RUN echo ✅ ✅ ✅ ✅ Successfully created dist at: && cd __dist__ && ls -d $PWD/*
ENTRYPOINT echo Successfully created dist at: && cd __dist__ && ls -d $PWD/*
