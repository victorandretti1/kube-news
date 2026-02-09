FROM node:18-bullseye

WORKDIR /app

# Ferramentas para build de pacotes nativos
RUN apt-get update && apt-get install -y \
    build-essential \
    python3 \
    make \
    g++ \
    libcairo2-dev \
    libpango1.0-dev \
    libjpeg-dev \
    libgif-dev \
    librsvg2-dev \
    && rm -rf /var/lib/apt/lists/*

# Copia dependências para usar cache de layer
COPY package*.json ./

# Instala dependências
RUN npm ci --unsafe-perm --legacy-peer-deps --verbose

# Copia código restante
COPY . .

EXPOSE 8080

CMD ["node", "server.js"]
