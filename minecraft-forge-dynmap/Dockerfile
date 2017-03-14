FROM merciless210/centos6-java8

RUN mkdir /minecraft

WORKDIR /minecraft

ENV MINECRAFT_VERSION 1.8.9
ENV FORGE_VERSION 11.15.1.1902-1.8.9

RUN curl -sS http://files.minecraftforge.net/maven/net/minecraftforge/forge/${MINECRAFT_VERSION}-${FORGE_VERSION}/forge-${MINECRAFT_VERSION}-${FORGE_VERSION}-installer.jar > /minecraft/forge-${MINECRAFT_VERSION}-${FORGE_VERSION}-installer.jar
RUN java -jar /minecraft/forge-${MINECRAFT_VERSION}-${FORGE_VERSION}-installer.jar --installServer
RUN rm -f /minecraft/forge-${MINECRAFT_VERSION}-${FORGE_VERSION}-installer.jar
RUN java -jar forge-1.8.9-11.15.1.1902-1.8.9-universal.jar
RUN curl -SL https://minecraft.curseforge.com/projects/dynmapforge/files/2380593/download -o /minecraft/mods/Dynmap-2.4-forge-1.8.9.jar
RUN curl -SL https://minecraft.curseforge.com/projects/forge-essentials-74735/files/2341980/download -o /minecraft/mods/forgeessentials-1.8.9-1.8.5.103-server.jar
RUN sed -i s/false/true/g /minecraft/eula.txt


EXPOSE 25565 8123

CMD /bin/bash
