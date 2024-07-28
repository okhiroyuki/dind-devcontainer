FROM mcr.microsoft.com/devcontainers/typescript-node:1-22

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
    curl \
    && apt-get clean -y && rm -rf /var/lib/apt/lists/*

RUN curl -fsSL https://raw.githubusercontent.com/devcontainers/features/main/src/docker-in-docker/install.sh | bash

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
    pre-commit \
    && apt-get clean -y && rm -rf /var/lib/apt/lists/*

VOLUME [ "/var/lib/docker" ]

ENTRYPOINT [ "/usr/local/share/docker-init.sh" ]

CMD [ "sleep", "infinity" ]
