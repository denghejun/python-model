# **********************
# docker build --no-cache --progress=plain -t python-model:v1.0.1 -f docker/python/Dockerfile .
# docker build --build-arg DIST_FILE_NAME=python-model.tar.gz --no-cache --progress=plain -t python-model:v1.0.1 -f docker/python/Dockerfile .
# docker run python-model:v1.0.1
# **********************
FROM python:3.7-slim-buster
ARG DIST_FILE_NAME=python-model.tar.gz
ENV SRC=./src/
ENV WORKDIR=/build
ENV DIST_FILE_PATH=${WORKDIR}/__dist__/${DIST_FILE_NAME}
COPY ${SRC} ${WORKDIR}
WORKDIR ${WORKDIR}
RUN python3 setup.py sdist --formats=gztar -d __dist__
RUN mv __dist__/*.tar.gz  ${DIST_FILE_PATH}
RUN echo ✅ ✅ ✅ ✅ Successfully created dist at: && cd __dist__ && ls -d $PWD/*
ENTRYPOINT echo Successfully created dist at: && cd __dist__ && ls -d $PWD/*
