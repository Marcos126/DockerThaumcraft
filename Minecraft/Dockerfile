FROM ubuntu:latest

# Crear un directorio para el servidor de Minecraft
WORKDIR /Thaumcraft

# Instalar wget
RUN apt update && apt install -y wget openjdk-8-jdk && apt clean 

# Aceptar el EULA
RUN echo "eula=true" > eula.txt

# Descargar e instalar Forge

RUN wget -O forge-installer.jar https://files.minecraftforge.net/maven/net/minecraftforge/forge/1.12.2-14.23.5.2855/forge-1.12.2-14.23.5.2855-installer.jar && \
    java -jar forge-installer.jar --installServer && \
    rm forge-installer.jar
    
# Exponer el puerto del servidor de Minecraft
EXPOSE 19890

# Iniciar el servidor de Minecraft con Forge

ENTRYPOINT [ "java" ]

CMD ["-Xmx1024M", "-Xms1024M", "-jar", "forge-1.12.2-14.23.5.2855.jar", "nogui"]