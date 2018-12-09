FROM centos:7.5.1804
ENV container docker

RUN yum update -y && \
    yum install -y epel-release && \
    yum install -y \
    openssh-server \
    openssh-clients \
    iproute \
    which \
    sudo \
    git \
    vim \
    ansible-2.4.2.0 \
    ansible-list-3.4.21 \
    jq \
    yamllint && \
    yum clean all
