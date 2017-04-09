## RUN CONTAINER with all Volumes and Ports 
```
docker run -it -p 25565:25565 -p 8123:8123 -v /data/config:/minecraft/config -v /data/logs:/minecraft/logs -v /data/world:/minecraft/world --name mc.forest merciless210/minecraft-forge-forestry
```
Container will open in BASH within the following dir "/minecraft". To start MC server use the following command:
```
java -jar -Xms1G -Xmx2G -d64 forge-1.11.2-13.20.0.2279-universal.jar
```
