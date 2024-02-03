# Minecraft server dockerfile for ubuntu
FROM ubuntu:latest

#setting up the workdir
WORKDIR /Minecraft
LABEL name="Minecraft"

#setting up the environment variables 
ARG DEBIAN_FRONTEND=noninteractive 


#installing java
RUN apt update && apt install -y\
    openjdk-17-jdk \
    wget \
    && apt clean    

#setting eula to true
RUN echo "eula=true" > eula.txt

#downloading the server.jar
RUN wget https://maven.minecraftforge.net/net/minecraftforge/forge/1.12.2-14.23.5.2860/forge-1.12.2-14.23.5.2860-installer.jar

#exposing the port
EXPOSE 28990

#running the server
RUN java -jar forge-1.12.2-14.23.5.2860-installer.jar --installServer

RUN rm forge-1.12.2-14.23.5.2860-installer.jar

ENTRYPOINT [ "java" ]

CMD ["-jar","minecraft_server.1.12.2.jar","nogui"]

