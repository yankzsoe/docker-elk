ARG ELASTIC_VERSION

# https://www.docker.elastic.co/
FROM docker.elastic.co/apm/apm-server:${ELASTIC_VERSION:-8.17.3}

# Add your elasticsearch plugins setup here
# Example: RUN elasticsearch-plugin install analysis-icu

USER root
RUN apt-get update \
 && apt-get install -y curl || apt --fix-broken install -y \
 && apt-get install -y curl \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*


# Kembali ke user default (apm-server) jika perlu
USER apm-server