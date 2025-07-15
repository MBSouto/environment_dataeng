FROM debian:bullseye-slim

# Instala dependências
RUN apt-get update && apt-get install -y \
    curl \
    unzip \
    ca-certificates \
    && rm -rf /var/lib/apt/lists/*

# Baixa o binário oficial do DuckDB CLI
RUN curl -L https://github.com/duckdb/duckdb/releases/download/v1.3.1/duckdb_cli-linux-amd64.zip -o duckdb.zip \
    && unzip duckdb.zip \
    && mv duckdb /usr/local/bin/duckdb \
    && chmod +x /usr/local/bin/duckdb \
    && rm duckdb.zip

# Define diretório de trabalho
WORKDIR /workspace

# Inicia com terminal interativo
ENTRYPOINT ["duckdb"]
