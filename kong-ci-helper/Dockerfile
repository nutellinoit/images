ARG NODE
FROM node:${NODE}
RUN apk add curl bash
RUN curl -sL https://github.com/kong/deck/releases/download/v1.7.0/deck_1.7.0_linux_amd64.tar.gz -o deck.tar.gz
RUN tar -xf deck.tar.gz -C /tmp
RUN cp /tmp/deck /usr/local/bin/
RUN npm config set user 0
RUN npm config set unsafe-perm true
RUN npm install -g node-gyp node-pre-gyp
RUN npm install -g insomnia-inso
RUN npm install -g kong-portal-cli
RUN curl -L --output /usr/local/bin/gitlab-runner "https://gitlab-runner-downloads.s3.amazonaws.com/latest/binaries/gitlab-runner-linux-amd64"
RUN chmod +x /usr/local/bin/gitlab-runner
RUN addgroup -g 1001 -S gitlab-runner && adduser -u 1001 -S gitlab-runner -G gitlab-runner -s /bin/bash
RUN gitlab-runner install --user=gitlab-runner --working-directory=/home/gitlab-runner