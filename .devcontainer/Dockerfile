FROM mcr.microsoft.com/devcontainers/python:3.12

ARG NODE_VERSION=20

RUN curl -fsSL https://deb.nodesource.com/setup_${NODE_VERSION}.x | bash - \
    && apt-get install -y nodejs

WORKDIR /workspace

# プロジェクト全体をコピー
COPY . .

# フロントエンドの依存関係をインストール
RUN if [ -f "frontend/package.json" ]; then \
    cd frontend && yarn install; \
fi

# バックエンドの依存関係をインストール
RUN if [ -f "backend/requirements.txt" ]; then \
    pip install -r backend/requirements.txt; \
fi

RUN node --version && npm --version && python --version

RUN apt-get update && apt-get install -y postgresql postgresql-contrib libpq-dev

CMD ["bash"]