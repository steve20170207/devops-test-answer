#stage 1 make a dev image able to pull source code and compile
FROM centos:7 as builder
RUN yum install -y maven git
WORKDIR /
RUN git clone https://github.com/ckannon/devops-test.git
WORKDIR  /devops-test
RUN mvn package 

#stage 2 to make a samller image to run java application
FROM openjdk:8-jre-alpine
WORKDIR  /
COPY --from=builder /devops-test/target/DevopsTest.jar /DevopsTest.jar 
COPY start.sh /
CMD /bin/sh start.sh
EXPOSE 8080
