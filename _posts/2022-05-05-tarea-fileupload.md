---
layout: post
categories: 
conToc: true
title: Tarea Fileupload
---



# Tarea Fileupload


En esta tarea  se va a realizar un _reverse shell_ subiendo un archivo ejecutable para que nuestra víctima se conecte al equipo del atacante al visitar una url.


Descárgate éste [fichero](https://raw.githubusercontent.com/pentestmonkey/php-reverse-shell/master/php-reverse-shell.php) , y guardalo como _shell.php_
Edítalo y cambia la ip por la de tu equipo
![](https://github.com/savalls/savalls.github.io/blob/main/assets/img/2022-05-11_shell_php01.png?raw=true)


Instala una imagen docker que contiene una web vulnerable, como la del proyecto [DVWA](https://dvwa.co.uk/) , donde subiremos el fichero.
Puedes construir tu imagen docker desde [aquí](https://github.com/digininja/DVWA).

```bash
$ git clone https://github.com/digininja/DVWA.git
```
Nos movemos dentro del directorio que acabamos de clonar y ejecutamos _docker run_ para construir nuestra imagen.

```bash
$ `docker run --rm -it -p 80:80 vulnerables/web-dvwa`
```



Ahora, una vez en funcionamiento, nos dirigiremos a la sección _File Upload_  y subiremos el archivo _shell.php_ que hemos modificado anteriormente.


![](https://github.com/savalls/savalls.github.io/blob/main/assets/img/2022-05-11_shell_upload.png?raw=true)



En este punto, desde el equipo atacante, ejecuta en una consola el siguiente código:
```bash
$ nc -v -n -l -p 1234
```

![](https://github.com/savalls/savalls.github.io/blob/main/assets/img/2022-05-11_nc_listening.png?raw=true)


Ya solo queda esperar a que el equipo de la víctima, visite la ip del equipo atacante

![](https://github.com/savalls/savalls.github.io/blob/main/assets/img/2022-05-11_victima_web01.png?raw=true)


Y abrimos una conexión en la víctima.

![](https://github.com/savalls/savalls.github.io/blob/main/assets/img/2022-05-11_atacante_nc.png?raw=true)



