FROM merciless210/centos6-java8

RUN mkdir /minecraft

WORKDIR /minecraft

ENV MINECRAFT_VERSION 1.7.10
ENV FORGE_VERSION 10.13.4.1614-1.7.10
ENV FORESTRY_VERSION forestry_1.11.2-5.3.2.58.jar
ENV FORESTRY_URL https://minecraft.curseforge.com/projects/forestry/files/2333823/download
ENV INDUSTRIAL_VERSION industrialcraft-2-2.2.816-experimental.jar
ENV INDUSTRIAL_URL http://minecraft.curseforge.com/projects/industrial-craft/files/2286867/download
ENV BUILDCRAFT_VERSION buildcraft-7.1.21.jar
ENV BUILDCRAFT_URL http://www.mod-buildcraft.com/releases/BuildCraft/7.1.21/buildcraft-7.1.21.jar

RUN curl -sS http://files.minecraftforge.net/maven/net/minecraftforge/forge/${MINECRAFT_VERSION}-${FORGE_VERSION}/forge-${MINECRAFT_VERSION}-${FORGE_VERSION}-installer.jar > /minecraft/forge-${MINECRAFT_VERSION}-${FORGE_VERSION}-installer.jar
RUN java -jar /minecraft/forge-${MINECRAFT_VERSION}-${FORGE_VERSION}-installer.jar --installServer
RUN rm -f /minecraft/forge-${MINECRAFT_VERSION}-${FORGE_VERSION}-installer.jar
RUN java -jar forge-${MINECRAFT_VERSION}-${FORGE_VERSION}-universal.jar
RUN curl -SL https://minecraft.curseforge.com/projects/dynmapforge/files/2380593/download -o /minecraft/mods/Dynmap-2.4-forge-1.8.9.jar
RUN curl -SL https://minecraft.curseforge.com/projects/forge-essentials-74735/files/2341980/download -o /minecraft/mods/forgeessentials-1.8.9-1.8.5.103-server.jar
RUN sed -i s/false/true/g /minecraft/eula.txt

EXPOSE 25565 8123

CMD /bin/bash
