# Configuración de FormIt para el desarrollo 

Para crear y probar módulos de extensión en la aplicación de escritorio de FormIt, necesitará FormIt para Windows v17.0 o posterior.

### **Visualizar los paneles Editor de secuencia de comandos y Salida de la secuencia de comandos**

En el menú superior de FormIt, vaya a **Ventana** y active las casillas **Editor de secuencias de comandos** y **Salida de la secuencia de comandos**.

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/EnableDevelopmentWindows.PNG)

Los paneles Editor de secuencias de comandos y Salida de la secuencia de comandos aparecerán en la parte inferior de la ventana de FormIt.

Alterne entre estos paneles mediante los botones que aparecen en la parte inferior.

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/ScriptEditorDefaultState.PNG)

También puede organizar ambos paneles uno al lado del otro. Haga clic en el botón situado junto a la "x" en la esquina superior derecha para desenlazar uno de los paneles y, a continuación, arrastre y suelte los paneles uno junto al otro, como se muestra a continuación:

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/ScriptEditor+ScriptOutputConfiguration.gif)

### **Editor de secuencias de comandos**

El Editor de secuencias de comandos proporciona un entorno de desarrollo sencillo en el que puede escribir y probar código.

Además, esta herramienta almacena el código escrito en un archivo scratch.js en el directorio en el que se encuentra el archivo FormIt.exe.

En la parte superior, aparecen estos dos botones:

**Ejecutar** ![](<../../../.gitbook/assets/image (8) (1).png>): ejecuta todo el código escrito en la ventana.

**Ejecutar selección** ![](<../../../.gitbook/assets/image (52).png>): ejecuta solo las líneas de código seleccionadas o resaltadas.

### **Salida de la secuencia de comandos**

En la ventana Salida de la secuencia de comandos, se muestran los mensajes impresos en la consola desde los módulos de extensión.

Para borrar la salida, ejecute `console.clear();` en el Editor de secuencias de comandos.

## Trabajo con módulos de extensión de ejemplo

Después de [clonar un repositorio](cloning-a-sample-plugin.md) y [configurar un servidor web](hosting-a-plugin-on-a-local-server.md), ahora puede conseguir que los módulos de extensión locales se muestren en FormIt.

Puede cargar o instalar cualquiera de los módulos, aunque, en este ejercicio, instalará tanto un módulo de extensión basado en panel como uno basado en barra de herramientas. Imaginemos que el "http-server" de npm se ejecuta en el puerto 8080 que aloja los dos repositorios de ejemplo.

### **Carga frente a instalación**

`FormIt.LoadPlugin();` carga el módulo solo para la sesión actual. El módulo de extensión se descargará automáticamente cuando se cierre y se reinicie la aplicación.

Esta es una opción excelente para mostrar temporalmente un módulo de extensión a fin de probarlo solo en la sesión actual.

`FormIt.InstallPlugin();` permite que se conserve el módulo de extensión mediante una clave del Registro. Esto es ideal para los módulos de extensión que se utilizan con frecuencia de una sesión a otra.

En Windows, se utilizan las siguientes claves del Registro para conservar los módulos de extensión:

* Módulos de extensión: Computer\\HKEY_CURRENT_USER\\Software\\Autodesk\\FormIt 360\\Plugins\\InstalledPlugins

Utilice `FormIt.UninstallPlugin();` para desinstalar el módulo de extensión.

En los ejemplos siguientes, a menos que se indique lo contrario, puede utilizar las opciones de _instalación_ o _carga_ en función de si desea conservar o no los resultados del ejercicio.

### **Ejemplo de módulo de extensión de barra de herramientas: Flip Along**

En el editor de secuencias de comandos, ejecute lo siguiente:

Si se ejecuta un servidor local, introduzca lo siguiente:

* `FormIt.LoadPlugin("http://localhost:8080/FlipAlong");`

Si la carga se realiza desde el [repositorio de GitHub de FormIt](https://github.com/FormIt3D/), introduzca lo siguiente (se requiere una conexión a Internet):

* `FormIt.LoadPlugin("https://formit3d.github.io/FlipAlong");`

Debería aparecer la barra de herramientas de Flip Along en la parte superior de la ventana de la aplicación, como se muestra a continuación:

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FlipAlongToolbar.PNG)

### **Ejemplo de módulo de extensión de panel HTML: Properties Plus**

En el editor de secuencias de comandos, ejecute lo siguiente:

Si se ejecuta un servidor local, introduzca lo siguiente:

* `FormIt.LoadPlugin("http://localhost:8080/PropertiesPlus");`

Si la carga se realiza desde el [repositorio de GitHub de FormIt](https://github.com/FormIt3D/), introduzca lo siguiente (se requiere una conexión a Internet):

`FormIt.LoadPlugin("https://formit3d.github.io/PropertiesPlus");`

El panel Properties Plus debería aparecer a la derecha de la ventana de la aplicación, como se muestra a continuación:

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/PropertiesPlusPanel.png)

### **Ejemplo de módulo de extensión de cuadro de diálogo modal y sin modo**

Los módulos de extensión de cuadro de diálogo son únicos; solo se pueden cargar, pero no instalar.

En el editor de secuencias de comandos, ejecute lo siguiente:

Si se ejecuta un servidor local, introduzca lo siguiente:

* Modal: `FormIt.LoadPlugin("http://localhost:8080/FormItExamplePlugins/ModalDialog");`
* Sin modo: `FormIt.LoadPlugin("http://localhost:8080/FormItExamplePlugins/ModelessDialog");`

Si la carga se realiza desde el [repositorio de GitHub de FormIt](https://github.com/FormIt3D/), introduzca lo siguiente (se requiere una conexión a Internet):

* Modal: `FormIt.LoadPlugin("https://formit3d.github.io/FormItExamplePlugins/ModalDialog");`
* Modal: `FormIt.LoadPlugin("https://formit3d.github.io/FormItExamplePlugins/ModelessDialog");`

Debería aparecer el panel "Hello Block!" del ejemplo de panel HTML en la pantalla como un cuadro de diálogo modal o sin modo.
