FROM node:18.12.1

# Diretório de trabalho
WORKDIR /app

# Copia apenas os arquivos de dependência primeiro
COPY package*.json ./

# Instala dependências com logs detalhados e permissões corretas
RUN npm install --unsafe-perm --verbose

# Copia o restante do código
COPY . .

# Expõe a porta da aplicação
EXPOSE 8080

# Comando para iniciar a aplicação
CMD ["node", "server.js"]
