# syntax=docker/dockerfile:1

# image
FROM python:3.9

# create a non-root user
ARG USERNAME=user
RUN useradd --create-home --shell /bin/bash --no-log-init $USERNAME

# use non-root user
USER $USERNAME
WORKDIR /home/user
