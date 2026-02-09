FROM node:18.12.1

WORKDIR /app

# Instala ferramentas de build necessárias para pacotes nativos
RUN apt-get update && apt-get install -y build-essential python3 make g++

# Copia arquivos de dependência
COPY package*.json ./

# Instala dependências com logs detalhados e permissões corretas
RUN npm install --unsafe-perm --verbose

# Copia restante do código
COPY . .

EXPOSE 8080
CMD ["node", "server.js"]
