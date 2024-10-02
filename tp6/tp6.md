4.1 Creación de una BD SQL Server para nuestra App

![Descripción de la imagen](images/im1.jpg)
![Descripción de la imagen](images/im2.jpg)
![Descripción de la imagen](images/im3.jpg)
![Descripción de la imagen](images/im4.jpg)


4.2 Obtener nuestra App
A. Clonar el repo https://github.com/ingsoft3ucc/Angular_WebAPINetCore8_CRUD_Sample.git
B. Seguir las instrucciones del README.md del repo clonado prestando atención a la modificación de la cadena de conexión en el appSettings.json para que apunte a la BD creada en 4.1
C. Navegar a http://localhost:7150/swagger/index.html y probar uno de los controladores para verificar el correcto funcionamiento de la API.

![Descripción de la imagen](images/im5.jpg)
![Descripción de la imagen](images/im6.jpg)
![Descripción de la imagen](images/im7.jpg)
![Descripción de la imagen](images/im8.jpg)
![Descripción de la imagen](images/im9.jpg)
![Descripción de la imagen](images/im10.jpg)






4.3 Crear Pruebas Unitarias para nuestra API
A. En el directorio raiz de nuestro repo crear un nuevo proyecto de pruebas unitarias para nuestra API

![Descripción de la imagen](images/im11.jpg)

B. Instalar dependencias necesarias

![Descripción de la imagen](images/im12.jpg)

D. Renombrar archivo UnitTest1.cs por EmployeeControllerUnitTests.cs

![Descripción de la imagen](images/im13.jpg)

E. Editar el archivo EmployeeCrudApi.Tests/EmployeeCrudApi.Tests.csproj para agregar una referencia a nuestro proyecto de EmployeeCrudApi reemplazando su contenido por
![Descripción de la imagen](images/im14.jpg)

G. Verificar que se hayan ejecutado correctamente las pruebas
![Descripción de la imagen](images/im15.jpg)


H. Verificar que no estamos usando una dependencia externa como la base de datos.


I. Modificar la cadena de conexión en el archivo appsettings.json para que use un usuario o password incorrecto y recompilar el proyecto EmployeeCrudApi
![Descripción de la imagen](images/im16.jpg)
![Descripción de la imagen](images/im17.jpg)
![Descripción de la imagen](images/im18.jpg)



K. En la carpeta de nuestro proyecto EmployeeCrudApi.Tests volver a correr las pruebas
L. Verificar que se hayan ejecutado correctamente las pruebas inclusive sin tener acceso a la BD, lo que confirma que es efectivamente un conjunto de pruebas unitarias que no requieren de una dependencia externa para funcionar.
![Descripción de la imagen](images/im19.jpg)

M. Modificar la cadena de conexión en el archivo appsettings.json para que use el usuario y password correcto y recompilar el proyecto EmployeeCrudApi
![Descripción de la imagen](images/im20.jpg)

N. Verificar que nuestro proyecto vuelve a tener acceso a la BD navegando a http://localhost:7150/swagger/index.html y probando uno de los controladores:
![Descripción de la imagen](images/im21.jpg)

4.4 Creamos pruebas unitarias para nuestro front de Angular:
A. Nos posicionamos en nuestro proyecto de front, en el directorio EmployeeCrudAngular/src/app
![Descripción de la imagen](images/im22.jpg)


B. Editamos el archivo app.component.spec.ts reemplazando su contenido por:
![Descripción de la imagen](images/im23.jpg)

C. Creamos el archivo employee.service.spec.ts reemplazando su contenido por:
![Descripción de la imagen](images/im24.jpg)

D. Editamos el archivo employee.component.spec.ts ubicado en la carpeta employee reemplazando su contenido por:
![Descripción de la imagen](images/im25.jpg)

E. Editamos el archivo addemployee.component.spec.ts ubicado en la carpeta addemployee reemplazando su contenido por:
![Descripción de la imagen](images/im26.jpg)

F. En el directorio raiz de nuestro proyecto EmployeeCrudAngular ejecutamos el comando
![Descripción de la imagen](images/im27.jpg)

H. Vemos que los tests se ejecutaron correctamente:
![Descripción de la imagen](images/im28.jpg)

I. Verificamos que no esté corriendo nuestra API navegando a http://localhost:7150/swagger/index.html y recibiendo esta salida:
![Descripción de la imagen](images/im29.jpg)

4.5 Agregamos generación de reporte XML de nuestras pruebas de front.
Haremos los siguientes pasos para prepararnos:
A. Instalamos dependencia karma-junit-reporter
![Descripción de la imagen](images/im30.jpg)

B. En el directorio raiz de nuestro proyecto (al mismo nivel que el archivo angular.json) creamos un archivo karma.conf.js con el siguiente contenido
![Descripción de la imagen](images/im31.jpg)

C. Ejecutamos nuestros test de la siguiente manera:
ng test --karma-config=karma.conf.js --watch=false --browsers ChromeHeadless
![Descripción de la imagen](images/im32.jpg)
![Descripción de la imagen](images/im33.jpg)



4.6 Modificamos el código de nuestra API y creamos nuevas pruebas unitarias:
![Descripción de la imagen](images/im34.jpg)
![Descripción de la imagen](images/im35.jpg)
![Descripción de la imagen](images/im36.jpg)
![Descripción de la imagen](images/im37.jpg)



B. Crear las pruebas unitarias necesarias para validar las modificaciones realizadas en el código
![Descripción de la imagen](images/im38.jpg)

