FROM python:3.9.16-slim-buster
USER root

# environment
ENV LANG="ja_JP.UTF-8" \
    LANGUAGE="ja_JP:ja" \
    LC_ALL="ja_JP.UTF-8"
ENV TZ JST-9

RUN apt-get update && apt-get install -y --no-install-recommends \
    tzdata \
    curl \
    vim \
    zip 

RUN pip install --upgrade pip
RUN pip install --upgrade setuptools

# パッケージのインストール
COPY requirements.txt /root
WORKDIR /root
RUN pip install --no-cache-dir -r requirements.txt