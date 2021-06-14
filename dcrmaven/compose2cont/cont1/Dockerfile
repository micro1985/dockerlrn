FROM ubuntu:18.04

RUN apt update
RUN apt install default-jdk maven git -y
RUN git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git /home/user/boxfuse/
RUN mvn package -f /home/user/boxfuse/pom.xml
RUN mkdir /home/user/bxf/
RUN cp /home/user/boxfuse/target/hello-1.0.war /home/user/bxf/
WORKDIR /home/user/bxf/

CMD ["/bin/bash"]