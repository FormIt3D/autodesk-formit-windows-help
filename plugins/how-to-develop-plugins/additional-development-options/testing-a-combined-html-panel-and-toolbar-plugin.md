# Probar un módulo de extensión combinado de panel HTML y barra de herramientas

Puede probar fácilmente los módulos de extensión en curso mediante el [Editor de secuencias de comando](../advanced-development/setting-up-formit-for-development.md) integrado en FormIt para Windows.

Es recomendable utilizar `FormIt.LoadPlugin("URL");` al realizar pruebas, ya que carga temporalmente los módulos de extensión para esta sesión (desaparecerán cuando se reinicie FormIt).&#x20;

Una vez finalizada las pruebas, puede conservar el módulo de extensión entre sesiones mediante `FormIt.InstallPlugin("URL");`.

**FormIt para Windows v17 y versiones más recientes**

****

### **Módulos de extensión de barra de herramientas**

Cargue el módulo de extensión en FormIt para ver la interfaz de usuario más reciente y probar las últimas funciones:

* `FormIt.LoadPlugin("http://localhost:8080/YourPluginName");`

Realice algunos cambios y, a continuación, cargue de nuevo el módulo de extensión con el comando indicado anteriormente.

Puede cargar muchas instancias del mismo módulo de extensión en la sesión actual a medida que realiza la prueba, cada una con su propia interfaz de usuario.

Asegúrese de utilizar la última instancia de la interfaz de usuario para asegurarse de que está probando los cambios más recientes.



### **Módulos de extensión de panel HTML**

Cargue el módulo de extensión en FormIt para ver la interfaz de usuario más reciente y probar las últimas funciones:

* `FormIt.LoadPlugin("http://localhost:8080/YourPluginName");`

Realice algunos cambios y, a continuación, haga clic con el botón derecho en el panel y seleccione "Forzar recarga" para volver a cargar el panel con las últimas secuencias de comandos HTML y CSS.

****

### **Obtener una vista preliminar del módulo de extensión con Plugin Manager**

Una vez cargado el módulo, consulte el [capítulo anterior](../advanced-development/previewing-a-plugin-in-the-plugin-manager.md) de esta guía.

****

### **Forzar la limpieza de la memoria caché web para los archivos .JSON**

Si modifica el título o la descripción dentro del archivo manifest.json de un módulo de extensión o un repositorio, es posible que deba forzar la eliminación de la memoria caché en FormIt para Windows a fin de que se apliquen esos cambios la próxima vez que vuelva a cargar Plugin Manager.

FormIt para Windows almacena su memoria caché web aquí; deberá activar los elementos ocultos en el Explorador de Windows para ver la carpeta AppData.

* C:\Usuarios\user\AppData\Local\Autodesk\FormIt 360\QtWebEngine\Default

Para eliminar la memoria caché web, simplemente elimine la carpeta "Default" indicada anteriormente y, a continuación, vuelva a cargar Plugin Manager para ver los títulos y las descripciones actualizados.
