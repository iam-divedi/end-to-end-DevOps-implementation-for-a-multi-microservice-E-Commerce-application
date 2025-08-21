FROM python:3.12-slim-bookworm AS baseFROM python:3.12-slim-bookworm AS base

WORKDIR /user/src/app

COPY requirements.txt ./

RUN pip install --upgrade pip
RUN pip install -r requirements.txt


COPY . .

ENTRYPOINT ["python","recommendation_server.py"]


WORKDIR /user/src/app

COPY requirements.txt ./

RUN pip install --upgrade pip
RUN pip install -r requirements.txt


COPY . .

ENTRYPOINT ["python","recommendation_server.py"]

~                                                                                                                       ~                                                                                                                       ~                                                     
