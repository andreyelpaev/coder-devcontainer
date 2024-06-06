FROM registry.access.redhat.com/ubi9

USER root
RUN yum install -y yum-utils && \
    yum -y install zsh && \
    wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | zsh

# Set default shell to zsh
ENV SHELL /bin/zsh
