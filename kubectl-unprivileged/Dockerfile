FROM ubuntu:18.04

RUN apt update && apt install curl -y
ARG KUBECTL
RUN curl -L https://storage.googleapis.com/kubernetes-release/release/${KUBECTL}/bin/linux/amd64/kubectl -o /usr/local/bin/kubectl && \
    chmod +x /usr/local/bin/kubectl && \
    kubectl version --client \

ARG user=gitlab
ARG group=gitlab
ARG uid=1000
ARG gid=1000

ENV HOME=/home/gitlab/runner

RUN addgroup --group ${group} --gid ${gid} \
    && mkdir -p $HOME \
    && useradd -m -g ${group} -d ${HOME} -u ${uid} -l ${user} \
    && chown ${user}:${group} ${HOME}

USER ${user}
WORKDIR ${HOME}

ENTRYPOINT [ "/usr/local/bin/kubectl" ]
