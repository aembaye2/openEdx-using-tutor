FROM ubuntu:22.04

# Install dependencies
RUN apt-get update && apt-get install -y \
    python3 python3-pip git curl wget locales \
    docker.io docker-compose \
    && locale-gen en_US.UTF-8

# Set locale
ENV LANG=en_US.UTF-8 \
    LANGUAGE=en_US:en \
    LC_ALL=en_US.UTF-8

# Install pipx + Tutor
RUN pip3 install --no-cache-dir pipx && \
    pipx install tutor[full]

# Add user
RUN useradd -ms /bin/bash dev && adduser dev docker
USER dev
WORKDIR /home/dev
