# 1. Define a imagem base: um Linux leve que já vem com Node 20 instalado
FROM node:20-slim 

# 2. Define o "Working Directory": a pasta onde os comandos abaixo serão executados DENTRO do container
WORKDIR /app

# Instala dependências mínimas (opcional, mas ajuda em alguns casos)
RUN apt-get update -y && apt-get install -y --no-install-recommends \
    openssl \
    ca-certificates \
    && rm -rf /var/lib/apt/lists/*

# 3. Copia o arquivo de dependências primeiro (otimiza o cache do Docker)
COPY package*.json ./

# 4. Roda o comando para instalar as bibliotecas do seu projeto
RUN npm install

# 5. Copia todo o resto do seu código da pasta 'back' para dentro do container (/app)
COPY . .

# 6. Informa ao Docker que este container vai ouvir na porta 3000
# next roda na porta 3000 por padrão
EXPOSE 3000

# 7. Modo desenvolvimento com hot reload
CMD ["npm", "run", "dev"]