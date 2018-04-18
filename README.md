# DockerNifiMaki

# Construir la imagen :
```docker build -t bigdatamx/nifi  . ```

# Construir el Container :

```docker run --name nifi -v /{TU_PATH}/facturas:/opt/nifi/nifi-1.5.0/facturas -p 8080:8080 -p 8443:8443 -p 10000:10000 -p 5656:7070 -d  bigdatamx/nifi```


Ejemplo :

```docker run --name nifi -v /home/javier/facturas:/opt/nifi/nifi-1.5.0/facturas -p 8080:8080 -p 8443:8443 -p 10000:10000 -p 5656:7070 -d  bigdatamx/nifi```

En la etiqueta de -v ```{TU_PATH}``` colocar el path completo de donde se encuentran almacenados las facturas los xml.


# En el navegador poner la siguiente URL : 
```http://localhost:8080/nifi/```


# Cambiar el host del processor del POSTPredictionIOEventServer:

Colocar el host del server, ```NO PONER localhost```

```http://{TU_IP}:7070```

Ejemplo : 

```http://192.168.100.5:7070```


Para saber la ip, en la consola de la máquina tipear : ```ifconfig``` 


# Cambiar el PredictionIO Event Server App Key del processor del POSTPredictionIOEventServer , para saber la key tipear:
```pio app list```



# La ruta default en donde se encuentra las facturas es :
 ```/opt/nifi/nifi-1.5.0/facturas```

Se recomienda no cambiar esta ruta, que hace referencia al container.


# Comprobar que se esten almacenando, colocar en el navegador :

```http://localhost:7070/events.json?accessKey={KEY}```

Cambiar ```{KEY}```, por el  PredictionIO Event Server App Key.

