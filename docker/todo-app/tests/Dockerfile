# rode a partir da imagem do mjgargani/puppeteer:trybe1.0;
FROM mjgargani/puppeteer:trybe1.0

# Criando um diretório para trabalho
WORKDIR /app

# Copiando os jsons para o diretório de trabalho e instalando as dependências
COPY package*.json ./
RUN npm install

# adicione o arquivo node_modules.tar.gz à imagem;
ADD node_modules.tar.gz /app/

# copie todos os arquivos da pasta tests para a imagem. (você pode usar o caminho relativo, lembrando que a Dockerfile está em ./docker/todo-app/tests/Dockerfile);
COPY ./ ./

# inicie a aplicação com o comando npm test respeitando as seguintes restrições:
    # ao subir um container baseado na imagem buildada a partir desse Dockerfile, o comando npm deve ser rodado sempre;
    # ao subir um container baseado na imagem buildada a partir desse Dockerfile, deve ser possível sobrescrever o comando test.
ENTRYPOINT ["npm"]
CMD ["test"]