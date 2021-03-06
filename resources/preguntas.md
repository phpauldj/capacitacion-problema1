# Ejercicio 1
Capacitación: Git, bash y docker
Integrantes:
* Paul Carlos Taboada Casas
* Davis Palomino
* Pedro Vega

## Preguntas Part. 1:
1. ¿Qué es y para qué sirve GIT?
* Rpta: Es un Sistema de Control de Versiones, que ayuda a administracion las versiones del codigo de un proyecto de software.

2. ¿Que es Github o bitbucket?
* Rpta: Son repositorios de codigo que trabajan con sistemas de control de versiones, que se conectan a servidores remotos.

---

3. ¿Qué es y para qué sirve el SSH?
* Rpta: SSH o Secure Shell es un protocolo que falicita las comunicaciones seguras entre dos sistemas usando una arquitectura cliente/servidor, y que te permite a los usuarios conectarse a un host remotamente.

4. ¿Que pasa si cambio de PC? ¿Tendré que generar el SSH nuevamente?¿Por qué?
* Rpta: Si, ya que por cada pc se genera una clave publica y privada diferente que lo hace unica.

5. ¿Qué es markdown? ¿Para qué sirve?
* Rpta: Markdown es un lenguaje de marcado ligero creado por John Gruber que trata de conseguir la máxima legibilidad y facilidad de publicación tanto en su forma de entrada como de salida, inspirándose en muchas convenciones existentes para marcar mensajes de correo electrónico usando texto plano. Se distribuye bajo licencia BSD y se distribuye como plugin (o al menos está disponible) en diferentes sistemas de gestión de contenidos (CMS). Markdown convierte el texto marcado en documentos XHTML utilizando html2text creado por Aaron Swartz. Markdown fue implementado originariamente en Perl por Gruber, pero desde entonces ha sido traducido a multitud de lenguajes de programación, incluyendo PHP, Python, Ruby, Java y Common Lisp.

---

6. ¿Cómo inicializo y configuro un proyecto de git?
* Rpta: Se inicializa con git init, y se puede configurar git config, dentro de este tiene varias opciones como agregar un nombre y correo de usuario, que editor de texto se usa para abrir textos planos, generar abreviados de los comandos, el estilo, etc.

## Preguntas: Part. 2:
1. ¿Para qué ayuda el `git stash`?
* Rpta: Para guardar nuestros cambios en memoria local, para luego ser utilizados.

2. ¿Cuál es la diferencia entre `git stash pop` y `git stash apply`?
* Rpta: Git stash pop, puedes aplicar los cambios de tu ultimo stash local guardado y eliminarlo del almacenamiento. Git stash apply, aplica los cambios para un stash espcecifico sin ser eliminado.

3. ¿Qué significa el modo interactivo del `git rebase`?
* Rpta: El modo interactivo es poder gestionar los commits agregados hasta el momento del rebase, se puede modificar, mezclar, eliminar la lista de commits y otras opciones mas.

---

4. ¿Cual es la diferencia entre la shell y la terminal?
* Rpta: El shell es la linea de comandos que se ejecutan en una consola (terminal), que vendria a ser la interfaz para poder ejecutarlos.

5. ¿Que hace estos comandos? `git clone`, `git status`, `git add`, `git commit`, `git push`, `git checkout`, `git stash`, `git rebase`, `git merge`, `git branch`, `git push`
* Rptas:
* git clone, permite descargar un repositorio remoto de un servidor.
* git status, permite ver el estado de los cambios que se han realizado en la rama de un repositorio local.
* git add, permite agregar archivos del directorio de trabajo al area de preparacion o stage.
* git commit, permite confirmar que archivos pasaran del area de preparacion (stage) a la cabecera de la rama sobre el repositorio.
* git push, permite subir los cambios realizar en la rama al repositorio remoto.
* git checkout, permite moverte entre ramas de un repositorio.
* git stash, permite guardar cambias en tu memoria local.
* git rebase, permite gestionar los cambios de una rama sobre otra, se tienen varias opciones para ejecutar durante el proceso.
* git merge, permite mezclar los cambios de una rama a otra.
* git branch, permite crear una rama en un repositorio.

---

## Preguntas DOCKER: Part. 3:
1. ¿Porqué es necesario crear un contenedor con esta bandera -it ? ¿Qué pasa si no le pongo -it?
Por que te permite ingresar a la consola del contenedor de manera interactiva y asi poder ejecutar comandos shell, si no pones -it ejecuta el comando X y sale.

2. ¿Para qué sirve ejecutar el comando bash al ejecutar una imagen?
Para que ejecute el programa de consola y asi poder ejecutar comandos shell dentro del contenedor.

3. ¿Cuál es la diferencia entre docker ps y docker ps -a?
El docker ps te muestra los contenedores que estan corriendo y el ps -a todos los contenedores que existan.

4. Comando para Ejecutar el contenedor de Docker:
* docker run -it ptaboada/orbis-training-docker:0.2.0 bash

---

## Preguntas DOCKER: Part. 4:
1. ¿Cuál es la diferencia entre una imagen y un contenedor?
Una imagen vendria a ser una plantilla y el contenedor es una instancia de una imagen.

2. ¿Cómo listo las imágenes que hay en mi computadora?
Lo listo con el comando: docker images
Extra: para eliminar las imagenes crasheadas ejecutar el siguiente comando: docker rmi $(docker images | awk '/^<none>/ {print $3}')
Ref.: https://medium.com/@rasheedamir/docker-remove-all-untagged-images-58e2585ec270

3. ¿Cómo salgo de un contenedor de docker?
Ejecutando el comando exit dentro de la consola del contenedor.

4. ¿Se elimina el contenedor al salir de ella?
No

5. ¿Cómo elimino un contenedor?
Con el comando: docker rm [CONTAINER_ID]

6. ¿Para qué es necesario el flag `-i`, `-t`, `--rm`?
-i: modo interactivo, que te permite ejecutar los comandos shell dentro del contenedor.
-t: activa el termian, el cual seria la interfaz donde se ejecuta los comandos shell en el contenedor.
--rm: elimina el contenedor generado luego de ser detenido (no se visualiza en el docker ps -a).

---

7. ¿Cómo verifico que el archivo creado se encuentra en la imagen?
Para validar si el archivo ha sido creado, levantamos un contenedor de la imagen y ingresamos al contenedor para validar si el archivo ha sido creado.

8. ¿Cómo se comenta una linea de código en Dockerfile?
Con el caracter # (michi)

## Preguntas DOCKER: Part. 5:
1. ¿Qué es NGINX?
Nginx ​ es un servidor web/proxy inverso ligero de alto rendimiento y un proxy para protocolos de correo electrónico.​​ Es software libre y de código abierto, licenciado bajo la Licencia BSD simplificada; también existe una versión comercial distribuida bajo el nombre de Nginx Plus.​

2. ¿Cómo expongo puertos en docker?
En docker cli con el option: -p
En docker-compose con el atributo "ports:" dentro del servicio.

3. ¿Cómo especifico los puertos al levantar un contenedor (docker run)?
Con el comando -p "[NRO.PUERTO EXPUESTO:NRO.PUERTO CONTAINER]"

4. ¿Cómo hago 'forward' al levantar un contenedor (docker run)?
Exponer a un puerto externo relacionado al puerto del contenedor de docker por medio de la opcion -p

---

## Preguntas DOCKER: Part. 6:

1. ¿Es necesario especificar el `workdir` en docker?, ¿Porqué?

No es necesario, pero es de gran ayuda para especificar una ruta raiz del proyecto y no estar ingresando constantemente.

2. ¿Que hacen los siguientes comandos? 
- `docker ps`: Muestra los containers activos de docker.
- `docker pull`: Baja las imagenes publicadas en docker hub.
- `docker push`: Sube los cambios realizado a la imagen de docker.
- `docker rm`: Eliminar un container.
- `docker rmi`: Eliminar imagenes.
- `docker run`: Ejecuta un container en base a una imagen.
- `docker tag`: Permite agregar o modificar tag a las imagenes docker.
- `docker search`: Permite buscar las imagenes existentes en docker hub según un termino.
- `docker login`: Permite logearte a tu repositorio de docker.
- `docker exec`: Permite ejecutar comando dentro de un container activo.
- `docker build`: Permite construir imagenes en base a un dockerfile.
- `docker inspect`: Permite ver caracteristicas de los objetos de docker (imagenes, redes y containers).
- `docker network`: Permite administrar redes dentro de docker.

---

## Preguntas DOCKER: Part. 7:

1. ¿Qué es bash? ¿Qué significa?
- Es un programa informático, cuya función consiste en interpretar órdenes, y un lenguaje de consola. BASH significa The Bourne-Again Shell

2. ¿Cómo ejecuto un archivo bash?
- Con el comando bash, sh o ./ (si tiene permisos de ejecucion) en linux

3. ¿Qué pasa si no especifico en un `.sh`, la linea `#!/bin/bash`?
No pasa nada, igual al usar el comando sh o bash lo interpreta como codigo bash

4. ¿Se puede cambiar el modo bash (`/bin/bash`) a otro tipo de ejecución?
Si, pero no ejecutaria la linea de comandos por que no podria entenderlo

5. ¿Cómo se envía variables de entorno por Docker CLI y docker-compose?
Usando el docker cli se añade el parametro -e y en el docker-compose en la seccion environment