FROM solsson/kafka:0.11.0.1

RUN apt-get update && apt-get install -y wget --no-install-recommends; \
    rm -rf /var/lib/apt/lists/*; \
    rm -rf /var/log/dpkg.log /var/log/alternatives.log /var/log/apt
