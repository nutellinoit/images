ARG NODE
FROM node:${NODE}
RUN curl -sL https://github.com/kong/deck/releases/download/v1.7.0/deck_1.7.0_linux_amd64.tar.gz -o deck.tar.gz
RUN tar -xf deck.tar.gz -C /tmp
RUN cp /tmp/deck /usr/local/bin/
RUN npm install -g insomnia-inso
RUN npm install -g kong-portal-cli
