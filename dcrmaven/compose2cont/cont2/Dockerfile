FROM ubuntu:18.04

ENV CATALINA_HOME /usr/share/apache-tomcat-9.0.40
ENV PATH $CATALINA_HOME/bin:$PATH
RUN mkdir -p "$CATALINA_HOME"

RUN apt update
RUN apt install default-jre -y
ADD https://mirror.datacenter.by/pub/apache.org/tomcat/tomcat-9/v9.0.40/bin/apache-tomcat-9.0.40.tar.gz /home/user/
RUN tar -xf /home/user/apache-tomcat-9.0.40.tar.gz -C /usr/share/

EXPOSE 8080

WORKDIR /home/user/apache-tomcat-9.0.40/webapps/

CMD ["catalina.sh", "run"]