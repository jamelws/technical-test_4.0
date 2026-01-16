FROM wso2/wso2mi:4.0.0-ubuntu

USER root

RUN apt-get update && apt-get install -y --no-install-recommends \
    tcpdump \
    procps \
    curl \
 && rm -rf /var/lib/apt/lists/*

EXPOSE 8290 8253

USER wso2carbon
