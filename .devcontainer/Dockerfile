FROM registry.access.redhat.com/ubi9/toolbox

USER root

RUN yum install -y yum-utils && \
    yum-config-manager --add-repo https://download.docker.com/linux/rhel/docker-ce.repo && \
    yum install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y

RUN systemctl enable docker

RUN ln -s /usr/libexec/docker/cli-plugins/docker-compose /usr/bin/docker-compose

ENV LANG=en_US.UTF-8


RUN curl https://raw.githubusercontent.com/creationix/nvm/master/install.sh | bash && \
    source ~/.bashrc && \ 
    nvm install lts/*
    
RUN yum install dotnet-sdk-7.0 dotnet-runtime-7.0 aspnetcore-runtime-7.0 -y

RUN useradd coder \
    --create-home \
    --shell=/bin/bash \
    --groups=docker \
    --uid=1000 \
    --user-group && \
    echo "coder ALL=(ALL) NOPASSWD:ALL" >>/etc/sudoers.d/nopasswd

USER coder
