# radiko_recorder

Un script de Python y un contenedor de Docker para grabar programas de Radiko.

## Description

### Script de Python para grabar radiko
Al ejecutarlo, se especifica el ID del área mediante una variable de entorno, y la emisora, el nombre del programa (utilizado para guardar el archivo) y el tiempo de grabación mediante argumentos del script.
Ejemplo: Para grabar el programa "hoge" de TBS en Tokio durante 10 minutos.
```
RADIKO_AREA_ID=JP13 python src/app.py TBS hoge 10
```

### Contenedor docker

Al construir y ejecutar la imagen, empezará a aceptar solicitudes HTTP en el puerto 8080.
Ejemplo: Para grabar el programa "hoge" de TBS durante 10 minutos.
```
curl '127.0.0.1:8080/record?station=TBS&program=hoge&rtime=10'
```
El área está especificada mediante la variable de entorno RADIKO_AREA_ID al momento de construir la imagen. Cambiándola según sea necesario antes de construir.


## Author

[keisuke yamanaka](https://github.com/1012ky)
