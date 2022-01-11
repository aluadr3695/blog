---
layout: post
categories: 
conToc: true
title: Práctica Dockerhub
---




# Práctica Dockerhub

En esta práctica aprenderás a crear imágenes de tus containers y a subirlos a un repositorio para que las tengas siempre disponibles.

El primer paso será crear una cuenta en [Dockerhub](https://hub.docker.com/).

![](https://github.com/savalls/savalls.github.io/blob/main/assets/img/dockerhub_portada.png?raw=true)




Ahora desde una consola de texto te logueas dentro de la cuenta que acabas de crear
```bash
$ docker login
```
Ejecutas _*docker images*_, y podrás comprobar el nombre de los repositorios que estarán listados en la columna __REPOSITORY__ 

![](https://github.com/savalls/savalls.github.io/blob/main/assets/img/docker_images.png?raw=true)



Seguídamente tendrás que preparar la nomenclatura de la imagen que vas a subir, de la siguiente manera **nombre\_de\_usuario/nombre\_del\_repositorio:etiqueta** y generas un tag de la imagen referida para nombrarla.

```bash
docker tag chapter2 savalls/chapter2:v1
```

Si vuelves a listar ahora _docker images_, verás la nueva versión que se ha creado

![](https://github.com/savalls/savalls.github.io/blob/main/assets/img/docker_images2.png?raw=true)

Y ya finalmente, solo te queda ejecutar docker push **nombre\_de\_usuario/nombre\_del\_repositorio:etiqueta**

![](https://github.com/savalls/savalls.github.io/blob/main/assets/img/docker_push_chapter2.png?raw=true)



Si ahora navegas hasta tu cuenta en dockerhub y revisas tu repositorio, podrás comprobar que la imagen se encuentra lista para ser instalada en otro container.

![](https://github.com/savalls/savalls.github.io/blob/main/assets/img/dockerhub_chapter2.png?raw=true)

