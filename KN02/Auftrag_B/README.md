``` sh
cd db
docker build -t kn02b-db .
```

``` sh
cd web
docker build -t kn02b-web .
```

``` sh
docker run -d --name kn02b-web -p 8080:80 --link kn02b-db:db kn02b-web
```



Telnet
![alt text](image-2.png)


Verbindung zu db und info
![alt text](image.png)
![alt text](image-1.png)