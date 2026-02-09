FROM node:18.12.1

WORKDIR /app

# Ferramentas de build para pacotes nativos
RUN apt-get update && apt-get install -y build-essential python3 make g++

# Copia dependências
COPY package*.json ./

# Instala dependências npm
RUN npm cache clean --force
RUN npm install --unsafe-perm --verbose --legacy-peer-deps

# Copia código restante
COPY . .

EXPOSE 8080

CMD ["node", "server.js"]
