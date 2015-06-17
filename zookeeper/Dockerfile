FROM centos:7
ADD confluent.repo /etc/yum.repos.d/confluent.repo
RUN yum -y install confluent-platform-2.10.4
RUN yum -y install java-1.7.0-openjdk
RUN yum -y install python-setuptools
RUN yum -y install openssh-server
RUN yum -y clean all
RUN easy_install supervisor 
RUN echo "server.1=kafka-docker:2888:3888" >> /etc/kafka/zookeeper.properties
RUN echo "advertised.host.name=kafka-docker" >> /etc/kafka/server.properties
RUN echo "127.0.0.1   kafa-broker" >> /etc/hosts
ADD supervisord.conf /etc/supervisord.conf
VOLUME ["/var/lib/zookeeper","/var/lib/kafka"]
EXPOSE 80 2181 9092 22 9022
CMD ["/bin/supervisord"]

