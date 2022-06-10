# Depuración

La depuración de un módulo de extensión de FormIt requiere procedimientos diferentes en función del motor que se esté depurando. (Para obtener más información sobre los motores, consulte la [sección anterior](client-side-vs-web-side-engines.md)).

### **Depuración del cliente (FormIt)**

Para depurar en el código de FormIt, que se aplica tanto a los módulos de extensión basados en barras de herramientas como aquellos basados en paneles, puede añadir una línea al código para que se muestre el depurador de JS integrado, como se indica a continuación:

`debugger`

![](../../../.gitbook/assets/debugger.gif)

### **Depuración web (HTML)**

Los módulos de extensión de FormIt de paneles ofrecen depuración de la interfaz de usuario basada en HTML, ya que los paneles son fundamentalmente sitios web HTML con estilos y secuencias de comandos.

Para depurar código HTML para los módulos de extensión integrados en un panel, incluidas las secuencias de comandos y los estilos:

* **FormIt para Windows 2021.1 y versiones posteriores**
   * Haga clic con el botón derecho en la página HTML del módulo de extensión y haga clic en "Depurar" para que se muestre el depurador HTML integrado de la aplicación.

![](../../../.gitbook/assets/debugpanelplugin.gif)

* **FormIt para Web**
   * Utilice el método abreviado F12 o Ctrl + Mayús + I para que se muestre el depurador HTML del navegador.

![](../../../.gitbook/assets/debugonweb.gif)

