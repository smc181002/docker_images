FROM centos:8
RUN dnf install 'dnf-command(config-manager)' -y
RUN dnf config-manager --add-repo=https://download.docker.com/linux/centos/docker-ce.repo
RUN dnf install docker-ce --nobest -y
RUN echo "export DOCKER_HOST=`/sbin/ip route|awk '/default/ { print $3 }'`:4243" | cat >> $HOME/.bashrc

RUN yum install -y wget
RUN yum install -y httpd
RUN yum install git -y

