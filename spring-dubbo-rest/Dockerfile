from centos:latest

EXPOSE 8086 8086

ADD jdk-8u111-linux-x64.tar.gz /usr/java/

ADD target/spring-dubbo-rest-1.0-SNAPSHOT-prod.tar.gz /usr/dubbo-server/spring-dubbo-rest/

#RUN yum install -y dos2unix && dos2unix /usr/dubbo-server/spring-dubbo-rest/startup.sh

RUN cd /usr/dubbo-server/spring-dubbo-rest/ && sed -i 's/java/\/usr\/java\/jdk1.8.0_111\/bin\/java/g' startup.sh startupd.sh && chmod 777 startup.sh startupd.sh

ENTRYPOINT cd /usr/dubbo-server/spring-dubbo-rest/ && sh startupd.sh