# syntax=docker/dockerfile:1

# image
FROM debian:bullseye-slim

# setup the environment
ENV LANG=C.UTF-8

# create a non-root user
ARG USERNAME=user
RUN useradd --create-home --shell /bin/bash --no-log-init $USERNAME

# give user sudo privileges
RUN apt-get update \
    && apt-get install -y sudo \
    && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
    && chmod 0440 /etc/sudoers.d/$USERNAME

# use non-root user
USER $USERNAME
WORKDIR /home/user
