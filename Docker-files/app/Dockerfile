FROM openjdk:11 AS BUILD_IMAGE

RUN apt update && apt install maven -y && apt install git -y

RUN git clone https://github.com/siva185/vprofile-project.git

RUN cd vproifle-project && git checkout docker 

RUN mvn install


FROM tomcat:9-jre11

RUN rm -rf /usr/local/tomcat/webapps/*

COPY --from=BUILD_IMAGE /vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080

CMD [ "catalina.sh", "run" ]
