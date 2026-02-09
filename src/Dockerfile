# Imagem base do Node
FROM node:18.12.1

# Define o diretório de trabalho dentro do container
WORKDIR /app

# Copia os arquivos de dependência
COPY package*.json ./

# Instala dependências de forma determinística
RUN npm ci --unsafe-perm --legacy-peer-deps --verbose

# Copia o restante do código da aplicação
COPY . .

# Expõe a porta que a aplicação vai rodar
EXPOSE 8080

# Comando para iniciar a aplicação
CMD ["node", "server.js"]
