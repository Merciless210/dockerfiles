FROM merciless210/centos6-java8 

RUN mkdir /minecraft
#RUN mkdir /minecraft/mods

WORKDIR /minecraft

ENV MINECRAFT_VERSION 1.12.2
ENV FORGE_VERSION 14.23.3.2681
#Disabled - unable to find correct version or dynmap
#ENV DYNMAP_URL https://www.curseforge.com/minecraft/mc-mods/dynmapforge/download/3068729/file
#ENV DYNMAP_VERSION Dynmap-3.1-beta4-forge-1.12.2.jar
#Used to download DYNMAP
#RUN curl -SL ${DYNMAP_URL} -o /minecraft/mods/${DYNMAP_VERSION}
#Used to download MC
RUN curl -sS http://files.minecraftforge.net/maven/net/minecraftforge/forge/${MINECRAFT_VERSION}-${FORGE_VERSION}/forge-${MINECRAFT_VERSION}-${FORGE_VERSION}-installer.jar > /minecraft/forge-${MINECRAFT_VERSION}-${FORGE_VERSION}-installer.jar
RUN java -jar /minecraft/forge-${MINECRAFT_VERSION}-${FORGE_VERSION}-installer.jar --installServer
RUN rm -f /minecraft/forge-${MINECRAFT_VERSION}-${FORGE_VERSION}-installer.jar

RUN java -jar /minecraft/minecraft_server.${MINECRAFT_VERSION}.jar
RUN sed -i s/false/true/g /minecraft/eula.txt 

VOLUME ["/dynmap","/world","/logs"]

EXPOSE 25565 8123

CMD /bin/bash
