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

Para acceder ....

## Parametros


| Nombre                    | Descripcion                                     | Valor |
| ------------------------- | ----------------------------------------------- | ----- |
| `global.imageRegistry`    | Global Docker image registry                    | `""`  |

