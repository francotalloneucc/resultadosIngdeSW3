1- Objetivos de Aprendizaje
Adquirir conocimientos acerca de las herramientas de despliegue y releases de aplicaciones.
Configurar este tipo de herramientas.
Comprender el concepto de recurso en Azure
Comprender los conceptos básicos de Release Pipelines en Azure DevOps.
Configurar un Release Pipeline para automatizar despliegues en diferentes entornos-
2- Unidad temática que incluye este trabajo práctico
Este trabajo práctico corresponde a la unidad Nº: 3 (Libro Continuous Delivery: Cap 10)

3- Consignas a desarrollar en el trabajo práctico:
Los despliegues (deployments) de aplicaciones se pueden realizar en diferentes tipos de entornos
On-Premise (internos) es decir en servidores propios.
Nubes Públicas, ejemplo AWS, Azure, Gcloud, etc.
Plataformas como servicios (PaaS), ejemplo Heroku, Google App Engine, AWS, Azure WebApp, etc
En este práctico haremos despliegue a Plataforma como Servicio utilizando Azure Web Apps
4- Desarrollo:

4.1. Crear una cuenta en Azure

![Descripción de la imagen](im1.jpg)

4.2. Crear un recurso Web App en Azure Portal y navegar a la url provista

![Descripción de la imagen](im2.jpg)
![Descripción de la imagen](im3.jpg)
![Descripción de la imagen](im4.jpg)
![Descripción de la imagen](im5.jpg)
![Descripción de la imagen](im6.jpg)
![Descripción de la imagen](im7.jpg)
![Descripción de la imagen](im8.jpg)
![Descripción de la imagen](im9.jpg)
![Descripción de la imagen](im10.jpg)
![Descripción de la imagen](im11.jpg)
![Descripción de la imagen](im12.jpg)
![Descripción de la imagen](im13.jpg)
![Descripción de la imagen](im14.jpg)





4.3. Actualizar Pipeline de Build para que use tareas de DotNetCoreCLI@2 como en el pipeline clásico, luego crear un Pipeline de Release en Azure DevOps con CD habilitada

Actualizamos el Pipeline de Build:

![Descripción de la imagen](im15.jpg)
![Descripción de la imagen](im16.jpg)

Luego creamos un Pipeline de Release:

![Descripción de la imagen](im17.jpg)
![Descripción de la imagen](im18.jpg)
![Descripción de la imagen](im19.jpg)
![Descripción de la imagen](im20.jpg)
![Descripción de la imagen](im21.jpg)





4.4. Optimizar Pipeline de Build:

![Descripción de la imagen](im22.jpg)
![Descripción de la imagen](im23.jpg)

4.5. Verificar el deploy en la url de la WebApp /weatherforecast

![Descripción de la imagen](im24.jpg)

4.6. Realizar un cambio al código del controlador para que devuelva 7 pronósticos, realizar commit, evaluar ejecución de pipelines de build y release, navegar a la url de la webapp/weatherforecast y corroborar cambio
Primero realizamos el cambio para que devuelva 7 pronosticos, yrealizamos el commit :

![Descripción de la imagen](im25.jpg)

Vemos que se ejecuta el pipeline de build y release:

![Descripción de la imagen](im26.jpg)
![Descripción de la imagen](im27.jpg)
![Descripción de la imagen](im28.jpg)



4.7. Clonar la Web App de QA para que contar con una WebApp de PROD a partir de un Template Deployment en Azure Portal y navegar a la url provista para la WebApp de PROD.

![Descripción de la imagen](im29.jpg)
![Descripción de la imagen](im30.jpg)
![Descripción de la imagen](im31.jpg)
![Descripción de la imagen](im32.jpg)
![Descripción de la imagen](im33.jpg)
![Descripción de la imagen](im34.jpg)
![Descripción de la imagen](im35.jpg)
![Descripción de la imagen](im36.jpg)
![Descripción de la imagen](im37.jpg)
![Descripción de la imagen](im38.jpg)
![Descripción de la imagen](im39.jpg)
![Descripción de la imagen](im40.jpg)



4.8. Agregar una etapa de Deploy a Prod en Azure Release Pipelines


![Descripción de la imagen](im41.jpg)
![Descripción de la imagen](im42.jpg)
![Descripción de la imagen](im43.jpg)
![Descripción de la imagen](im44.jpg)
![Descripción de la imagen](im45.jpg)
![Descripción de la imagen](im46.jpg)



4.9. Realizar un cambio al código del controlador para que devuelva 10 pronósticos, realizar commit, evaluar ejecución de pipelines de build y release, navegar a la url de la webapp/weatherforecast y corroborar cambio, verificar que en la url de la webapp_prod/weatherforecast se muestra lo mismo.

![Descripción de la imagen](im47.jpg)
![Descripción de la imagen](im48.jpg)


Evaluamos ejecución de pipeline de build y de reléase:

![Descripción de la imagen](im49.jpg)
![Descripción de la imagen](im50.jpg)
![Descripción de la imagen](im51.jpg)
![Descripción de la imagen](im52.jpg)


Corroboramos cambios:

![Descripción de la imagen](im53.jpg)

4.10. Modificar pipeline de release para colocar una aprobación manual para el paso a Producción.
Cambio el nro de weatherforecast a 5:

![Descripción de la imagen](im54.jpg)

vemos como se actualiza:

![Descripción de la imagen](im55.jpg)

pero el -prod sigue como antes:

![Descripción de la imagen](im56.jpg)

lo aprobamos:

![Descripción de la imagen](im57.jpg)
![Descripción de la imagen](im58.jpg)

y ahora el prod esta igual que el qa:

![Descripción de la imagen](im59.jpg)


4.14. Realizar un pipeline (no release) que incluya el deploy a QA y a PROD con una aprobación manual. El pipeline debe estar construido en YAML sin utilizar el editor clásico de pipelines ni el editor clásico de pipelines de release.

![Descripción de la imagen](im60.jpg)
![Descripción de la imagen](im61.jpg)
![Descripción de la imagen](im62.jpg)
![Descripción de la imagen](im63.jpg)





