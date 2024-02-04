FROM ubuntu:20.04

COPY . /api

WORKDIR /api

RUN apt-get update \
    && apt-get install -y python3-pip python3-dev \
    && cd /usr/local/bin \
    && ln -s /usr/bin/python3 python \
    && pip3 install --upgrade pip

RUN pip install -r requirements.txt
EXPOSE 5000

RUN pip install debugpy

ENV PYTONDONTWRITEBYTECODE 1
ENV PYTONUNBUFFERED 1
ENV DEBIAN_FROMTEND=noninteractive
# CMD ["python", "-m", "debugpy", "--listen", "0.0.0.0:5679", "app.py"]