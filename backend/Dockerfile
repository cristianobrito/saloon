# 1. Define a imagem base: um Linux leve que já vem com Node 20 instalado
FROM node:20-alpine 

# 2. Define o "Working Directory": a pasta onde os comandos abaixo serão executados DENTRO do container
WORKDIR /app

# 3. Copia o arquivo de dependências primeiro (otimiza o cache do Docker)
COPY package*.json ./

# 4. Roda o comando para instalar as bibliotecas do seu projeto
RUN npm install

# 5. Copia todo o resto do seu código da pasta 'back' para dentro do container (/app)
COPY . .

# 6. Informa ao Docker que este container vai ouvir na porta 3000
EXPOSE 3001

# 7. O comando que mantém o container vivo e rodando sua aplicação
CMD ["node", "server.js"]