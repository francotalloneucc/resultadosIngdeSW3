4- Desarrollo:
4.1 Modificar nuestro pipeline para incluir el deploy en QA y PROD de Imagenes Docker en Servicio Azure App Services con Soporte para Contenedores

![Descripción de la imagen](images/im1.jpg)
![Descripción de la imagen](images/im2.jpg)
![Descripción de la imagen](images/im3.jpg)
![Descripción de la imagen](images/im4.jpg)
![Descripción de la imagen](images/im5.jpg)


 4.2 Desafíos:
4.2.1 Agregar tareas para generar Front en Azure App Service con Soporte para Contenedores

![Descripción de la imagen](images/im6.jpg)
![Descripción de la imagen](images/im7.jpg)
![Descripción de la imagen](images/im8.jpg)
![Descripción de la imagen](images/im9.jpg)


4.2.2 Agregar variables necesarias para el funcionamiento de la nueva etapa considerando que debe haber 2 entornos QA y PROD para Back y Front.

![Descripción de la imagen](images/im10.jpg)

4.2.3 Agregar tareas para correr pruebas de integración en el entorno de QA de Back y Front creado en Azure App Services con Soporte para Contenedores.

![Descripción de la imagen](images/im11.jpg)
![Descripción de la imagen](images/im12.jpg)


4.2.4 Agregar etapa que dependa de la etapa de Deploy en QA que genere un entorno de PROD.

![Descripción de la imagen](images/im13.jpg)
![Descripción de la imagen](images/im14.jpg)
![Descripción de la imagen](images/im15.jpg)
![Descripción de la imagen](images/im16.jpg)
![Descripción de la imagen](images/im17.jpg)
![Descripción de la imagen](images/im18.jpg)


Agregamos aprobación manual:

![Descripción de la imagen](images/im19.jpg)
![Descripción de la imagen](images/im20.jpg)


4.2.5 Entregar un pipeline que incluya:
A) Etapa Construcción y Pruebas Unitarias y Code Coverage Back y Front
B) Construcción de Imágenes Docker y subida a ACR
C) Deploy Back y Front en QA con pruebas de integración para Azure Web Apps
D) Deploy Back y Front en QA con pruebas de integración para ACI
E) Deploy Back y Front en QA con pruebas de integración para Azure Web Apps con Soporte para contenedores
F) Aprobación manual de QA para los puntos C,D,E
G) Deploy Back y Front en PROD para Azure Web Apps
H) Deploy Back y Front en PROD para ACI
I) Deploy Back y Front en PROD para Azure Web Apps con Soporte para contenedores

![Descripción de la imagen](images/im21.jpg)
![Descripción de la imagen](images/im22.jpg)
![Descripción de la imagen](images/im23.jpg)








