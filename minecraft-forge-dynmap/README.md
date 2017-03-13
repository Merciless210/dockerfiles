#RUN CONTAINER
docker run -it -p 25565:25565 -p 8123:8123 --name mc.forge merciless210/minecraft-forge-dynmap

#PORTS
-p 25565:25565  [default minecraft server port]
-p 8123:8123    [default dynmap port]

#VOLUMES
-v /data/mods:/minecraft/mods
-v /data/world:/minecraft/world
-v /data/logs:/minecraft/logs
-v /data/dynmap:/minecraft/dynmap

#Dynmap commands
https://github.com/webbukkit/dynmap/wiki/Commands
