FROM centos:8

RUN yum install -y wget
RUN yum install -y httpd
RUN yum install git -y
RUN wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat/jenkins.repo
RUN rpm --import https://pkg.jenkins.io/redhat/jenkins.io.key
RUN dnf install jenkins -y
RUN yum install -y java
RUN yum install git -y
RUN echo "jenkins ALL=(ALL) NOPASSWD: ALL" | cat >> /etc/sudoers

# USER jenkins
# ENV USER jenkins

CMD /usr/sbin/httpd -DFOREGROUND
CMD java -jar /usr/lib/jenkins/jenkins.war --httpPort=8080

EXPOSE 8080
