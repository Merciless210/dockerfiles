#RUN CONTAINER with all VOLUMES and PORTS
docker run -it -p 25565:25565 -p 8123:8123 -v /data/dynmap:/minecraft/dynmap -v /data/logs:/minecraft/logs -v /data/world:/minecraft/world -v /data/mods:/minecraft/mods --name mc.forge merciless210/minecraft-forge-dynmap

Container will open in BASH within the following dir "/minecraft". To start MC server use the following command:
java -jar -Xms1G -Xmx4G -d64 forge-1.11.2-13.20.0.2214-universal.jar

To detach container press CTL+P, then CTL+Q
To reattach container use: docker attach [container.name] 
To find a running container name use: docker -ps 

#JAVA
-Xms1G -Xmx2G #Java's initial and maximum memory size in GB format
-Xms1024M -Xmx2048M #Java's initial and maximum memory size in MB format

#PORTS
-p 25565:25565  #default minecraft server port
-p 8123:8123    #default dynmap port

#VOLUMES
-v /data/world:/minecraft/world
-v /data/logs:/minecraft/logs
-v /data/dynmap:/minecraft/dynmap

#Dynmap commands
https://github.com/webbukkit/dynmap/wiki/Commands
