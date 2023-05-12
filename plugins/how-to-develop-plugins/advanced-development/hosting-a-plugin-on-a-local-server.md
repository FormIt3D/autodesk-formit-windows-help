# Alojar un módulo de extensión en un servidor local

Antes de obtener una vista preliminar de un módulo de extensión clonado en FormIt, debe alojarlo en un servidor local.

### **Ver el terminal en IDE**

Tiene la opción de iniciar el servidor en Visual Studio Code en lugar de en una ventana de terminal independiente.**** Antes de abrir un terminal, asegúrese de que la carpeta correcta esté abierta en Visual Studio Code.

View > Terminal (o utilice el método abreviado Ctrl + \`).

![](<../../../.gitbook/assets/image (11) (1).png>)

### Instalar un servidor HTTP

Un servidor HTTP que funciona correctamente es [http-server](https://www.npmjs.com/package/http-server) de npm.

En primer lugar, deberá descargar e instalar [NodeJS](https://nodejs.org/en/) si aún no está instalado.

Si se producen errores en los pasos siguientes, pruebe a reiniciar el equipo para completar la instalación de NodeJS.

En la solicitud de comando, introduzca lo siguiente para instalar el _http-server_ de npm globalmente (una instalación única).

* `npm install http-server -g`

![](<../../../.gitbook/assets/image (47).png>)

### Iniciar el servidor local

Una vez completada la instalación, ejecute el siguiente comando en el terminal para iniciar el "http-server" de npm:

* `http-server`

![](<../../../.gitbook/assets/image (84).png>)

Consejo 1: En caso de que surja algún problema al ejecutar el "http-server" (instalado de forma global o local), puede ser útil ejecutarlo directamente a través de npx, como se indica a continuación:

* `npx http-server`

Consejo 2: Para los usuarios de Windows 10 u 11, si se produce un error al ejecutar una secuencia de comandos en el nuevo equipo, esto puede deberse a que se ha desactivado la configuración. Para solucionar este problema, realice lo siguiente:

* Inicie una secuencia de comandos de PowerShell como administrador.
* Introduzca: `Set-ExecutionPolicy RemoteSigned`

### Desarrollar para la versión web de FormIt

Para el desarrollo para la versión web de FormIt, ejecute el siguiente comando en su lugar:

* `http-server --cors`

![](<../../../.gitbook/assets/image (10) (1).png>)

### Comprobar el servidor

Para comprobar el servidor, acceda a la siguiente dirección en el navegador web:

* http://localhost:8080

Debería ver los archivos de la carpeta de proyecto en la ventana del navegador.

**Si utiliza un servidor web distinto al de npm, la dirección o el puerto por defecto podrían ser diferentes.

![](<../../../.gitbook/assets/image (41).png>)
