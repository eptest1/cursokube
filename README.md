# cursokube


# Proyecto de Curso - Computación en la nube con virtualización liviana (Kubernetes)

Emilio Penna

<!--- app-name: WordPress -->

# Paquete para instalar WordPress
Wordpress es una plataforma popular para manejo de contenido web y blogs.

[Sitio](http://www.wordpress.org)

## TL;DR

Clonar el proyecto
```console
cd chart1-wp
helm install my-release  .
```

## Introduccion
Este chart instala una instancia de wordpress en un cluster Kubernetes usando el gestor de paquetes Helm. Tambien se incluye el despliegue de una base de datos mysql para que sea usada por wordpress.



## Prerequisitos

- Kubernetes 1.27+
- Helm 3.13.0+
- PV provisioner 

## Installing the Chart
Para instalar el chart con el nombre de release `my-release`:

```console
helm install my-release  .
```
Ese comando despliega Wordpress en el cluster Kubernetes con la configuración por defecto.
En la siguiente sección de Paraetros se listan los parametros que pueden ser configurados durante la instalación.


## Desinstalando el Chart

Para uninstall/delete el deployment `my-release`:

```console
helm delete my-release
```
Ese comando remueve todos los componentes Kubernetes asociados con el chart y borra el release

## Port forwarding

Una de las formas de acceder a la instancia de wordpress es realizar un port forwarding con el siguiente comando (suponiendo que el release se haya instalado con el nombre "my-release")":

```console
kubeclt port-forward deployment/my-release-wordpress  8000:80
```

## Parametros


| Nombre                    | Descripcion                                     | Valor |
| ------------------------- | ----------------------------------------------- | ----- |
| `global.imageRegistry`    | Global Docker image registry                    | `""`  |
|apps.wordpress.image|Imagen para usar de wordpress| wordpress|
|apps.wordpress.tag|tag de la imagen| 6.2.1-apache|
|apps.mysql.image|Imagen para usar de mysql|mysql|
|apps.mysql.tag|tag de la imagen de mysql| 8.0|
|persistence.size| tamaño de la unidad de persistencia para wordpress| 1Gi|
|db.name| nombre de la base de datos| wordpress|
|db.host| host de la base de datos| wordpress-mysql|
|db.user| usuario de la base de datos| wordpress|
|db.password| password del usuario de la base de datos| password|
|db.rootpassword| password del usuario root de la base de datos| password|
|db.persistence.size| tamaño de la unidad de persistencia para mysql| 1Gi|
|service.wordpress.internalport| puerto donde escucha el apache con wordpress| 80|
|resources.wordpress.memory| memoria asignada para el contenedor con wordpress| 500Mi|
|resources.wordpress.cpu| cpu asignada para el contenedor con wordpress| 500m|

