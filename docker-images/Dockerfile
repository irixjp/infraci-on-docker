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
    ansible \
    jq \
    ansible-list \
    yamllint && \
    yum clean all

RUN ssh-keygen -P '' -f ~/.ssh/id_rsa && \
    cat ~/.ssh/id_rsa.pub > ~/.ssh/authorized_keys && \
    mkdir -p ~/vagrant/infraci/.vagrant/machines/gitlab/virtualbox && \
    mkdir -p ~/vagrant/infraci/.vagrant/machines/gitlab-runner/virtualbox && \
    cp -p ~/.ssh/id_rsa ~/vagrant/infraci/.vagrant/machines/gitlab/virtualbox/private_key && \
    cp -p ~/.ssh/id_rsa ~/vagrant/infraci/.vagrant/machines/gitlab-runner/virtualbox/private_key

RUN useradd vagrant && \
    cp -rp cat ~/.ssh /home/vagrant && \
    chown -R vagrant:vagrant /home/vagrant/.ssh
