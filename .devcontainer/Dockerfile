FROM ubuntu:24.04

# タイムゾーンの設定
RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive TZ=Asia/Tokyo apt-get install -y tzdata && \
    ln -fs /usr/share/zoneinfo/$TZ /etc/localtime && \
    dpkg-reconfigure --frontend noninteractive tzdata
# ロケールの設定
RUN apt-get update && \
    apt-get install -y locales && \
    locale-gen ja_JP.UTF-8 && \
    update-locale LANG=ja_JP.UTF-8
# gitのインストール
RUN apt-get update && \
    apt-get install -y git
# TexLiveのインストール
RUN apt-get update && \
    apt-get install -y texlive-full
# sudoのインストール
RUN apt-get update && \
    apt-get install -y sudo
# aptのキャッシュを消す
RUN apt-get clean && \
    rm -rf /var/lib/apt/lists/*
