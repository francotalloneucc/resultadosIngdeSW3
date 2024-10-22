4- Desarrollo:
Prerequisitos:
Azure CLI instalado

![Descripción de la imagen](images/im1.jpg)

4.1 Modificar nuestro pipeline para construir imágenes Docker de back y front y subirlas a ACR
Desarrollo del punto 4.1:
4.1.1 Crear archivos DockerFile para nuestros proyectos de Back y Front
En la raiz de nuestro repo crear una carpeta docker con dos subcarpetas api y front, dentro de cada una de ellas colocar los dockerfiles correspondientes para la creación de imágenes docker en función de la salida de nuestra etapa de Build y Test

![Descripción de la imagen](images/im2.jpg)
![Descripción de la imagen](images/im3.jpg)
![Descripción de la imagen](images/im4.jpg)


Crear un recurso ACR en Azure Portal

![Descripción de la imagen](images/im5.jpg)

4.1.3 Modificar nuestro pipeline en la etapa de Build y Test
Luego de la tarea de publicación de los artefactos de Back agregar la tarea de publicación de nuestro dockerfile de back para que esté disponible en etapas posteriores:
Luego de la tarea de publicación de los artefactos de Front agregar la tarea de publicación de nuestro dockerfile de front para que esté disponible en etapas posteriores:

![Descripción de la imagen](images/im6.jpg)
![Descripción de la imagen](images/im7.jpg)


4.1.4 En caso de no contar en nuestro proyecto con una ServiceConnection a Azure Portal para el manejo de recursos, agregar una service connection a Azure Resource Manager como se indica en instructivo 5.2

![Descripción de la imagen](images/im8.jpg)


4.1.5 Agregar a nuestro pipeline variables

![Descripción de la imagen](images/im9.jpg)
![Descripción de la imagen](images/im10.jpg)


4.1.6 Agregar a nuestro pipeline una nueva etapa que dependa de nuestra etapa de Build y Test
Agregar tareas para generar imagen Docker de Back

![Descripción de la imagen](images/im11.jpg)
![Descripción de la imagen](images/im12.jpg)


4.1.7 - Ejecutar el pipeline y en Azure Portal acceder a la opción Repositorios de nuestro recurso Azure Container Registry. Verificar que exista una imagen con el nombre especificado en la variable backImageName asignada en nuestro pipeline

![Descripción de la imagen](images/im13.jpg)

4.1.8 - Agregar tareas para generar imagen Docker de Front (DESAFIO)
A la etapa creada en 4.1.6 Agregar tareas para generar imagen Docker de Front

![Descripción de la imagen](images/im14.jpg)
![Descripción de la imagen](images/im15.jpg)
![Descripción de la imagen](images/im16.jpg)

4.1.9 - Agregar a nuestro pipeline una nueva etapa que dependa de nuestra etapa de Construcción de Imagenes Docker y subida a ACR

Agregar variable secreta cnn-string-qa desde la GUI de ADO que apunte a nuestra BD de SQL Server de QA como se indica en el instructivo 5.3

![Descripción de la imagen](images/im17.jpg)

Agregar variables a nuestro pipeline:

![Descripción de la imagen](images/im18.jpg)

Agregar tareas para crear un recurso Azure Container Instances que levante un contenedor con nuestra imagen de back

![Descripción de la imagen](images/im19.jpg)

Configuramos el archivo Program.cs para que utilice la variable configurada

![Descripción de la imagen](images/im20.jpg)

Otorgamos permisos desde Azure CLI

![Descripción de la imagen](images/im21.jpg)
![Descripción de la imagen](images/im22.jpg)
![Descripción de la imagen](images/im23.jpg)


4.1.10 - Ejecutar el pipeline y en Azure Portal acceder al recurso de Azure Container Instances creado. Copiar la url del contenedor y navegarlo desde browser. Verificar que 
traiga datos.

![Descripción de la imagen](images/im24.jpg)


4.1.11 - Agregar tareas para generar un recurso Azure Container Instances que levante un contenedor con nuestra imagen de front (DESAFIO)
creamos una nueva variable

![Descripción de la imagen](images/im25.jpg)


Modificamos el codigo de nuestro front

![Descripción de la imagen](images/im26.jpg)
![Descripción de la imagen](images/im27.jpg)
![Descripción de la imagen](images/im28.jpg)
![Descripción de la imagen](images/im29.jpg)



Creamos nuevas variables y job:

![Descripción de la imagen](images/im30.jpg)
![Descripción de la imagen](images/im31.jpg)


resultado:

![Descripción de la imagen](images/im32.jpg)


4.1.12 - Agregar tareas para correr pruebas de integración en el entorno de QA de Back y Front creado en ACI.

![Descripción de la imagen](images/im33.jpg)
![Descripción de la imagen](images/im34.jpg)
![Descripción de la imagen](images/im35.jpg)
![Descripción de la imagen](images/im36.jpg)
![Descripción de la imagen](images/im37.jpg)


4.2.4 Agregar etapa que dependa de la etapa de Deploy en ACI QA y genere contenedores en ACI para entorno de PROD.


Agregamos etapa de PROD

![Descripción de la imagen](images/im38.jpg)
![Descripción de la imagen](images/im39.jpg)
![Descripción de la imagen](images/im40.jpg)
![Descripción de la imagen](images/im41.jpg)
![Descripción de la imagen](images/im42.jpg)



Además agregamos los permisos para el deployment

![Descripción de la imagen](images/im43.jpg)
