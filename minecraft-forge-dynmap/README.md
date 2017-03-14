## Version
```
merciless210/minecraft-forge-dynmap:latest
merciless210/minecraft-forge-dynmap:1.8.9 [includes Forge Essentials]
```

## RUN CONTAINER with all Volumes and Ports 
```
docker run -it -p 25565:25565 -p 8123:8123 -v /data/dynmap:/minecraft/dynmap -v /data/logs:/minecraft/logs -v /data/world:/minecraft/world --name mc.forge merciless210/minecraft-forge-dynmap
```
v 1.8.9
```
docker run -it -p 25565:25565 -p 8123:8123 -v /data/dynmap:/minecraft/dynmap -v /data/logs:/minecraft/logs -v /data/world:/minecraft/world --name mc.forge merciless210/minecraft-forge-dynmap:1.8.9
```

Container will open in BASH within the following dir "/minecraft". To start MC server use the following command:
```
java -jar -Xms1G -Xmx2G -d64 forge-1.11.2-13.20.0.2214-universal.jar
```
v 1.8.9
```
java -jar -Xms1G -Xmx2G -d64 forge-1.8.9-11.15.1.1902-1.8.9-universal.jar
```
To detach container press CTL+P, then CTL+Q
To reattach container use: ```docker attach [container.name]``` 
To find a running container name use: ```docker ps```

## Java parameters
```
-Xms1G -Xmx2G #Java's initial and maximum memory size in GB format
-Xms1024M -Xmx2048M #Java's initial and maximum memory size in MB format
```
For 32-bit systems remove:
```
-d64
```


## Ports
```
-p 25565:25565  #default minecraft server port
-p 8123:8123    #default dynmap port
```
If you need to change ports:
```
-p [port.on.host]:8123  #example -p 80:8123 
```

## Volumes
```
-v /data/world:/minecraft/world
-v /data/logs:/minecraft/logs
-v /data/dynmap:/minecraft/dynmap
```

## Dynmap commands
https://github.com/webbukkit/dynmap/wiki/Commands
