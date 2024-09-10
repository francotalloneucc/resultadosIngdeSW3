## Trabajo Práctico 4 - Azure Devops Pipelines

### 1- Objetivos de Aprendizaje
 - Adquirir conocimientos acerca de las herramientas de integración continua presentes en ADO.
 - Configurar este tipo de herramientas.
 - Implementar procesos de construcción automatizados simples.
 
### 2- Unidad temática que incluye este trabajo práctico
Este trabajo práctico corresponde a la unidad Nº: 3 (Libro Continuous Delivery: Cap 3)


CI (Continuous Integration), Continuous Deployment y Continuous Delivery son tres prácticas clave en la ingeniería de software que se utilizan para mejorar la calidad del software y acelerar el proceso de desarrollo. Aunque están relacionadas y a menudo se utilizan juntas, tienen diferencias clave:

**Continuous Integration (CI):**

CI es una práctica que implica la integración constante de cambios de código en un repositorio compartido por parte de varios desarrolladores.
Los desarrolladores envían regularmente su código al repositorio compartido (a menudo varias veces al día).
Cada vez que se envía código, se activan pruebas automáticas para verificar la calidad y la compatibilidad del código.
El objetivo principal de CI es detectar y resolver problemas de integración de código de manera temprana y continua, lo que evita la acumulación de errores.

**Continuous Delivery** 
En Continuous Delivery, después de que el código pasa por CI y se considera estable, se automatiza el proceso de empaquetado y preparación para la entrega.
Sin embargo, la entrega real al entorno de producción se realiza manualmente después de una revisión y aprobación humanas.

**Continuous Deployment (CD)**
Se refiere a la práctica de automatizar y acelerar el proceso de entrega de software al entorno de producción.
En Continuous Development, una vez que el código pasa por el proceso de CI y se considera estable, se automatiza la entrega del software al entorno de producción sin intervención manual adicional.
Esto implica la automatización de tareas como pruebas adicionales, empaquetado, despliegue y configuración en el entorno de producción.

En resumen, CI se centra en la integración continua de cambios de código y pruebas automáticas, mientras que Continuous Delivery y Continuous Deployment se centran en la automatización del proceso de entrega de software al entorno de producción, con Continuous Delivery deteniéndose antes de la entrega real y Continuous Deployment automatizando todo el proceso hasta la entrega al entorno de producción. 
Estas prácticas son esenciales en el desarrollo de software ágil y permiten la entrega rápida y confiable de software de alta calidad.

### 3- Consignas a desarrollar en el trabajo práctico:

 **Azure DevOps Pipelines**
  - Breve descripción de Azure DevOps Pipelines.
  - Tipos de Pipelines: Build y Deploy.
  - Diferencias entre editor clásico y YAML.
  - Agentes MS y Self-Hosted


#### 4- Pasos del TP
 - 4.1 Verificar acceso a Pipelines concedido
![Descripción de la imagen](imagen1.jpeg)


 - 4.2 Agregar en pipeline YAML una tarea de Publish. 
![Descripción de la imagen](imagen2.jpeg)
![Descripción de la imagen](imagen3.jpeg)
![Descripción de la imagen](imagen4.jpeg)


 - 4.3 Explicar por qué es necesario contar con una tarea de Publish en un pipeline que corre en un agente de Microsoft en la nube.

La tarea de Publish en un pipeline en la nube es esencial porque los agentes son efímeros y se eliminan al finalizar. Publicar los artefactos asegura su persistencia, facilita la distribución entre etapas y permite la trazabilidad y control de versiones.

 - 4.4 Descargar el resultado del pipeline y correr localmente el software compilado.
![Descripción de la imagen](imagen5.jpeg)
![Descripción de la imagen](imagen6.jpeg)
![Descripción de la imagen](imagen7.jpeg)


 - 4.5 Habilitar el editor clásico de pipelines. Explicar las diferencias claves entre este tipo de editor y el editor YAML.
![Descripción de la imagen](imagen8.jpeg)


 - 4.6 Crear un nuevo pipeline con el editor clásico. Descargar el resultado del pipeline y correr localmente el software compilado.
![Descripción de la imagen](imagen9.jpeg)
![Descripción de la imagen](imagen10.jpeg)
![Descripción de la imagen](imagen11.jpeg)
![Descripción de la imagen](imagen12.jpeg)
![Descripción de la imagen](imagen13.jpeg)
![Descripción de la imagen](imagen14.jpeg)




 - 4.7 Configurar CI en ambos pipelines (YAML y Classic Editor). Mostrar resultados de la ejecución automática de ambos pipelines al hacer un commit en la rama main.

Classic Editor:
![Descripción de la imagen](imagen15.jpeg)
![Descripción de la imagen](imagen16.jpeg)



yaml:
![Descripción de la imagen](imagen17.jpeg)
![Descripción de la imagen](imagen18.jpeg)
![Descripción de la imagen](imagen19.jpeg)
![Descripción de la imagen](imagen20.jpeg)



 - 4.8 Explicar la diferencia entre un agente MS y un agente Self-Hosted. Qué ventajas y desventajas hay entre ambos? Cuándo es conveniente y/o necesario usar un Self-Hosted Agent?

La diferencia entre un agente de Microsoft (MS) y un agente Self-Hosted radica en quién gestiona el servidor donde corre el agente:

Agente MS (Microsoft-Hosted): Es administrado por Microsoft, se aprovisiona automáticamente en la nube y se elimina al finalizar la tarea.

Ventajas: Configuración rápida, sin mantenimiento, siempre actualizado.
Desventajas: Tiempo limitado de ejecución, almacenamiento limitado, menos control sobre la configuración del entorno.

Agente Self-Hosted: Está alojado y gestionado por el propio usuario en sus servidores o infraestructura.

Ventajas: Control total sobre la configuración del entorno, sin límites estrictos de tiempo o almacenamiento, acceso a recursos locales.
Desventajas: Requiere mantenimiento, actualizaciones y recursos propios.

Es conveniente usar un Self-Hosted Agent cuando se necesita acceso a recursos específicos de la red local o control total del entorno de ejecución (por ejemplo, en pipelines que requieren hardware especializado o aplicaciones personalizadas).


 - 4.8 Crear un Pool de Agentes y un Agente Self-Hosted
![Descripción de la imagen](imagen21.jpeg)
![Descripción de la imagen](imagen22.jpeg)


 - 4.9 Instalar y correr un agente en nuestra máquina local.
![Descripción de la imagen](imagen23.jpeg)
![Descripción de la imagen](imagen24.jpeg)
![Descripción de la imagen](imagen25.jpeg)
![Descripción de la imagen](imagen26.jpeg)




 - 4.10 Crear un pipeline que use el agente Self-Hosted alojado en nuestra máquina local.
![Descripción de la imagen](imagen27.jpeg)
![Descripción de la imagen](imagen28.jpeg)



 - 4.11 Buscar el resultado del pipeline y correr localmente el software compilado.
![Descripción de la imagen](imagen29.jpeg)


 - 4.12 Crear un nuevo proyecto en ADO clonado desde un repo que contenga una aplicación en Angular como por ejemplo https://github.com/ingsoft3ucc/angular-demo-project.git
![Descripción de la imagen](imagen30.jpeg)
![Descripción de la imagen](imagen31.jpeg)



 - 4.13 Configurar un pipeline de build para un proyecto de tipo Angular como el clonado.
![Descripción de la imagen](imagen32.jpeg)
![Descripción de la imagen](imagen33.jpeg)



 - 4.14 Habilitar CI para el pipeline.
![Descripción de la imagen](imagen34.jpeg)


 - 4.15 Hacer un cambio a un archivo del proyecto (algún cambio en el HTML que se renderiza por ejemplo) y verificar que se ejecute automáticamente el pipeline.
![Descripción de la imagen](imagen35.jpeg)


 - 4.16 Descargar el resultado del pipeline y correr en un servidor web local el sitio construido.
![Descripción de la imagen](imagen36.jpeg)


 - 4.17 Mostrar el antes y el después del cambio.
![Descripción de la imagen](imagen37.jpeg)
![Descripción de la imagen](imagen38.jpeg)



#### 5- Presentación del trabajo práctico.
Subir un doc al repo con las capturas de pantalla de los pasos realizados y colocar en el excel de repos (https://docs.google.com/spreadsheets/d/1mZKJ8FH390QHjwkABokh3Ys6kMOFZGzZJ3-kg5ziELc/edit?gid=0#gid=0) la url del proyecto de AzureDevops.

#### 6- Criterio de Calificación
Los pasos 4.1 al 4.11 representan un 60% de la nota total, los pasos 4.12 al 4.17 representan el 40% restante

