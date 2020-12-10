FROM alpine/git
WORKDIR /app
RUN git clone https://github.com/shasidhar-bridgeitsol/test.git 

FROM maven:3.5-jdk-8-alpine
WORKDIR /app
COPY --from=0 /app/test/app 
RUN mvn install 

FROM openjdk:8-jre-alpine
WORKDIR /app
COPY --from=1 /app/target/pring-boot-web.jar /app 
CMD ["java -jar pring-boot-web.jar"] 
