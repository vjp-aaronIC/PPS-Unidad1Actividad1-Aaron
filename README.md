# PPS-Unidad1Actividad1-Aaron

## Levantar eclipse con docker

He levantado un entorno gráfico de eclipse con docker con lo siguiente comandos:

```bash
sudo mkdir -p  $HOME/docker/eclipse/datos
sudo chown -R alumno $HOME/docker/eclipse
sudo chgrp -R alumno $HOME/docker/eclipse
```

```bash
export DISPLAY=:0
xhost +10.0.4.110 
```

```bash
docker run -ti --rm \
           -e DISPLAY=$DISPLAY \
           -e artifactory_host='10.0.4.110:8080'\
	   --name eclipse \
           -v /tmp/.X11-unix:/tmp/.X11-unix \
           -v `pwd`:/workspace \
           -v $HOME/docker/eclipse/datos:/home/developer \
           dockeruc/eclipse	

```

Este comando es para arrancar un contenedor docker que tenga las siguientes variables:

- DISPLAY con el valor de la variable del sistema $DISPLAY.
- artifactory_host con la ip y el puerto donde quiero levantar eclipse.

Y con unos volumenes.

## Instalar extensiones

Sonar: es una extensión que ayuda al desarrollador a tener un código de mejor calidad.
Checkstyle: ayuda al desarrollador a seguir unos estándares en java.

He instalado desde el marketplace de eclipse la extensión de sonar y la extensión de checkstyle.

![](imagenes/extensiones_1.png)
![](imagenes/extensiones_2.png)

## Prueba de entornos

He ejecutado y compilado el código de una calculadora.

![](imagenes/calculadora_1.png)

Debbug:

![](imagenes/calculadora_debbug.png)
