FROM centos:8

RUN yum install -y openssh-server
RUN yum install -y openssh-clients
RUN yum install -y java
RUN ssh-keygen -t rsa -f /etc/ssh/ssh_host_rsa_key -N ''
RUN ssh-keygen -t dsa -f /etc/ssh/ssh_host_dsa_key -N ''
RUN echo root:passwd@123 | chpasswd
RUN sed 's@session\s*required\s*pam_loginuid.so@session optional pam_loginuid.so@g' -i /etc/pam.d/sshd

ENV NOTVISIBLE "in users profile"
RUN echo "export VISIBLE=now" >> /etc/profile
RUN curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl
RUN mv kubectl /usr/bin/
RUN chmod +x /usr/bin/kubectl 

COPY ./files/ca.crt /root/
COPY ./files/client.key /root/
COPY ./files/client.crt /root/
RUN mkdir root/.kube/
COPY ./files/config /root/.kube/

EXPOSE 22
CMD ["/usr/sbin/sshd", "-D", "&"]
