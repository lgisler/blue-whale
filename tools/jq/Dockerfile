FROM ubuntu:18.04 AS pipeline
LABEL Description="Dockerfile for configuring templated files"
USER root

# Install jq
RUN apt-get update && \
    apt-get --assume-yes install jq
