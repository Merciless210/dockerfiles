## RUN CONTAINER with all Volumes and Ports 
```
docker run -it -p 25565:25565 -v /data/config:/minecraft/config -v /data/logs:/minecraft/logs -v /data/world:/minecraft/world --name mc.forest merciless210/minecraft-forge-forestry
```
Container will open in BASH within the following dir "/minecraft". To start MC server use the following command:
```
java -jar -Xms1G -Xmx2G -d64 forge-1.7.10-10.13.4.1614-1.7.10-universal.jar
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
```-d64```

## Ports
```
-p 25565:25565  #default minecraft server port
```
If you need to change ports:
```
-p [port.on.host]:25565  #example -p 80:8123 
```

## Volumes
```
-v /data/world:/minecraft/world
-v /data/logs:/minecraft/logs
-v /data/dynmap:/minecraft/config
```
If you run into any permission issues you can use add ```:Z``` at the end of those volumes.
Example: ```-v /data/world:/minecraft/world:Z```
