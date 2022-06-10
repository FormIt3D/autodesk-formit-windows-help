# Introducción a los módulos de extensión

![](../.gitbook/assets/gg4.gif)

Los módulos de extensión son complementos de software personalizados que amplían las funciones principales de FormIt. Pueden mejorar, potenciar y simplificar los flujos de trabajo de modelado 3D en FormIt.&#x20;

Los módulos de extensión permiten generar objetos, realizar modificaciones en objetos existentes o extraer información sobre un objeto. También pueden utilizar interfaces web enriquecidas para mostrar datos y proporcionar controles y entradas directamente en la aplicación.&#x20;

## Acceso a módulos de extensión

Los módulos de extensión están disponibles en [Plugin Manager](how-to-use-plug-ins.md#plugin-manager) en las versiones web y de escritorio de FormIt, siempre que esté conectado a Internet. Los módulos de extensión están formados por una serie de archivos y carpetas alojados en GitHub o en un servidor local cuando se crea uno propio.&#x20;

![](../.gitbook/assets/c17.PNG)

### Los módulos de extensión requieren acceso a Internet

Los módulos de extensión externos (aquellos no hospedados localmente) requieren una conexión a Internet para cargarse inicialmente. Esto implica lo siguiente:

* Los módulos de extensión externos no se cargarán si no se detecta conexión a Internet al iniciar FormIt. Una vez cargados, algunos módulos de extensión externos pueden seguir trabajando en modo sin conexión en esa sesión, pero es posible que otros no funcionen hasta que se restablezca la conectividad.&#x20;
* Los módulos de extensión externos cargan el código más reciente del servidor en cada ejecución, por lo que sus funciones se actualizarán cada vez que el autor publique un cambio. Los módulos de extensión se cargan de forma asíncrona, lo que significa que su orden en la interfaz de FormIt puede cambiar en cada nueva sesión.

## Código abierto

Los módulos de [Plugin Manager](how-to-use-plug-ins.md#plugin-manager) son de código abierto, por lo que se pueden utilizar de forma gratuita, además de publicar y compartir fácilmente; también puede busca otros módulos de extensión en GitHub para descubrir cómo se han creado.&#x20;

Si es desarrollador y desea obtener más información sobre cómo publicar módulos de extensión, consulte [Alojamiento de un módulo de extensión en GitHub](how-to-develop-plugins/advanced-development/hosting-a-plugin-on-github.md).&#x20;

Si desea crear un módulo de extensión para uso privado, puede desarrollarlo y alojarlo mediante un servicio local. Para obtener más información, consulte [Uso de un IDE. ](how-to-develop-plugins/advanced-development/using-an-ide.md)

![](../.gitbook/assets/c18.PNG)



## Contáctenos

Si necesita ayuda con los módulos de extensión de FormIt, publique sus comentarios en el [foro de FormIt](https://forums.autodesk.com/t5/formit-forum/bd-p/142?profile.language=es).

![](../.gitbook/assets/c19.PNG)

&#x20;

&#x20;
