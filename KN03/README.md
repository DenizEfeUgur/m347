Netzwek erstellen
``` sh
docker network create --subnet=172.19.0.0/16 tbz

docker run -dit --name busybox1 --net tbz --ip 172.18.0.4 -p 8082:8080 busybox
docker run -dit --name busybox2 --net tbz --ip 172.18.0.5 -p 8083:8080 busybox
docker run -dit --name busybox3 --net tbz --ip 172.18.0.2 -p 8080:8080 busybox
docker run -dit --name busybox4 --net tbz --ip 172.18.0.3 -p 8081:8080 busybox

```

**docker inspect**
![alt text](image-10.png)


1. Docker exec -it busybox1 sh 
2. Ip route show default
![alt text](image.png)
busybox 3 hat den gleichen default gateway

- ping busybox2
![alt text](image-1.png)

- ping busybox2
![alt text](image-2.png)

- ping 172.18.0.1
![alt text](image-4.png)

- ping 172.18.0.2
![alt text](image-3.png)


### Busybox3

1. docker exec -it busybox3 sh
2. ip route show default
![alt text](image-5.png)

- ping busybox1
![alt text](image-6.png)

- ping busybox4
![alt text](image-7.png)

- ping 172.18.0.4
![alt text](image-8.png)

- ping 172.18.0.3
![alt text](image-9.png)


## Schlussfolgerung

Meine Schlussfolgerung ist, dass wenn sich Container im selben Netzwerk befinden, können sie miteinader kommunnizieren. Der Unterschied lag darin, dass sich die Container beim KN02 nicht im gleichen Netzwerk befunden haben, sondern mit dem Link sich verknüpft haben.

## KN02
- Die beiden Container befanden sich in dem gleichen Netzwerk wo ich mich befunden habe. Sprich im TBZ Netz
- Und sie konnten miteinadner kommunizieren, da sie mit dem link miteinader verknüft waren.