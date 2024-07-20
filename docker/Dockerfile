# ベースイメージとしてDebian Slimを使用
FROM debian:bookworm-slim

# 必要なパッケージのインストール
RUN apt-get update && apt-get install -y \
    curl \
    fonts-powerline \
    ca-certificates \
    --no-install-recommends && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Starshipのインストール
RUN curl -sS https://starship.rs/install.sh | sh -s -- --yes

COPY .config/starship.toml /root/.config/starship.toml

# Starshipの設定をZshの初期化ファイルに追加
RUN echo 'eval "$(starship init bash)"' >> ~/.bashrc
