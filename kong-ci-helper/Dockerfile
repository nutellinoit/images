ARG NODE
FROM node:${NODE}
RUN apk add curl wget bash git openssh-client
RUN curl -sL https://github.com/kong/deck/releases/download/v1.7.0/deck_1.7.0_linux_amd64.tar.gz -o deck.tar.gz
RUN tar -xf deck.tar.gz -C /tmp
RUN cp /tmp/deck /usr/local/bin/
RUN npm config set user 0
RUN npm config set unsafe-perm true
RUN npm install -g node-gyp node-pre-gyp
RUN npm install -g insomnia-inso
RUN npm install -g kong-portal-cli
RUN npm install -g speccy
RUN wget https://github.com/mikefarah/yq/releases/download/v4.9.6/yq_linux_amd64.tar.gz -O - |\
      tar xz && mv yq_linux_amd64 /usr/bin/yq
RUN chmod +x /usr/bin/yq
RUN yq --version