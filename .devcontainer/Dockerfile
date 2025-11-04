FROM ubuntu:22.04 AS build
WORKDIR /app

RUN apt-get update && \
  apt-get install -y \
  build-essential \
  wget \
  cmake \
  git \
  ca-certificates \
  ffmpeg \
  libsdl2-dev \
  && rm -rf /var/lib/apt/lists/* /var/cache/apt/archives/*

RUN git clone https://github.com/davidjlbailey/whisper.cpp.git
RUN make -C whisper.cpp base.en

ENV PATH=/app/whisper.cpp/bin:$PATH
ENTRYPOINT [ "bash", "-c" ]
