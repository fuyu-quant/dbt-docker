FROM python:3.9.13-buster
USER root

# environment
ENV LANG="ja_JP.UTF-8" \
    LANGUAGE="ja_JP:ja" \
    LC_ALL="ja_JP.UTF-8"
ENV TZ JST-9

RUN apt-get update && apt-get install -y --no-install-recommends \
    tzdata \
    curl \
    zip

RUN curl -OL https://github.com/duckdb/duckdb/releases/download/v0.6.1/duckdb_cli-osx-universal.zip
RUN unzip duckdb_cli-osx-universal.zip


RUN apt-get install -y vim less
RUN pip install --upgrade pip
RUN pip install --upgrade setuptools

# パッケージのインストール
COPY requirements.txt /root
WORKDIR /root
RUN pip install --no-cache-dir -r requirements.txt