FROM merciless210/centos6-java8 

RUN mkdir /minecraft

WORKDIR /minecraft

ENV MINECRAFT_VERSION 1.11.2
ENV FORGE_VERSION 13.20.0.2214

RUN curl -sS http://files.minecraftforge.net/maven/net/minecraftforge/forge/${MINECRAFT_VERSION}-${FORGE_VERSION}/forge-${MINECRAFT_VERSION}-${FORGE_VERSION}-installer.jar > /minecraft/forge-${MINECRAFT_VERSION}-${FORGE_VERSION}-installer.jar
RUN java -jar /minecraft/forge-${MINECRAFT_VERSION}-${FORGE_VERSION}-installer.jar --installServer
RUN rm -f /minecraft/forge-${MINECRAFT_VERSION}-${FORGE_VERSION}-installer.jar
RUN curl -SL https://minecraft.curseforge.com/projects/dynmapforge/files/2380603/download -o /minecraft/mods/Dynmap-2.4-forge-1.11.2.jar
RUN java -jar /minecraft/minecraft_server.1.11.2.jar
RUN sed -i s/false/true/g /minecraft/eula.txt 

VOLUME ["/dynmap","/world","/logs"]

EXPOSE 25565 8123 

CMD /bin/bash
