FROM node:18-bullseye

WORKDIR /app

# Ferramentas para build de pacotes nativos
RUN apt-get update && apt-get install -y build-essential python3 make g++ && rm -rf /var/lib/apt/lists/*

# Copia dependências
COPY package*.json ./

# Limpa cache e instala dependências
RUN npm cache clean --force \
    && npm install --unsafe-perm --legacy-peer-deps --verbose

# Copia código restante
COPY . .

EXPOSE 8080

CMD ["node", "server.js"]
