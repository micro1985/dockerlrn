FROM ubuntu:18.04

ENV CATALINA_HOME /usr/share/apache-tomcat-9.0.46
ENV PATH $CATALINA_HOME/bin:$PATH
ENV http_proxy=http://192.168.5.9:8080
ENV https_proxy=http://192.168.5.9:8080
ENV no_proxy=localhost,127.0.0.1
#ENV NO_PROXY=localhost,127.0.0.1

RUN mkdir -p "$CATALINA_HOME"

RUN apt update
RUN apt install apt-utils -y
RUN apt install default-jdk -y
RUN apt install maven -y
RUN apt install git -y
RUN git config --global https.proxy http://192.168.5.9:8080
RUN git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git /home/user/boxfuse/
RUN mvn package -f /home/user/boxfuse/pom.xml -DproxySet=true -DproxyHost=192.168.5.9 -DproxyPort=8080
ADD https://mirror.datacenter.by/pub/apache.org/tomcat/tomcat-9/v9.0.46/bin/apache-tomcat-9.0.46.tar.gz /home/user/
RUN tar -xf /home/user/apache-tomcat-9.0.46.tar.gz -C /usr/share/
RUN cp /home/user/boxfuse/target/hello-1.0.war $CATALINA_HOME/webapps/
EXPOSE 8080
CMD ["catalina.sh", "run"]
