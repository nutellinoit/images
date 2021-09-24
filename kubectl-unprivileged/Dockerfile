FROM alpine:3

RUN apk add curl ca-certificates --no-cache --update
ARG KUBECTL=v1.20.7
RUN curl -L https://storage.googleapis.com/kubernetes-release/release/${KUBECTL}/bin/linux/amd64/kubectl -o /usr/local/bin/kubectl && \
    chmod +x /usr/local/bin/kubectl && \
    kubectl version --client

RUN addgroup gitlab -g 1000
RUN mkdir -p /home/gitlab/runner
RUN adduser -g "Gitlab User" -h /home/gitlab/runner -u 1000 -D gitlab -G gitlab
RUN chown gitlab:gitlab /home/gitlab/runner

USER gitlab
WORKDIR /home/gitlab/runner

ENTRYPOINT [ "/usr/local/bin/kubectl" ]
