# Imagem base do Node
FROM node:18.12.1

# Define o diretório de trabalho dentro do container
WORKDIR /app

# Instala ferramentas de compilação necessárias para pacotes nativos
RUN apt-get update && apt-get install -y build-essential python3 make g++

# Copia os arquivos de dependência (package.json e package-lock.json)
COPY package*.json ./

# Instala dependências npm com logs detalhados e permissões corretas
RUN npm install --unsafe-perm --verbose

# Copia o restante do código da aplicação
COPY . .

# Expõe a porta que sua aplicação vai rodar
EXPOSE 8080

# Comando para iniciar a aplicação
CMD ["node", "server.js"]
