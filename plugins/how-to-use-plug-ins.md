# Cómo utilizar módulos de extensión

![](<../.gitbook/assets/g3 (1).gif>)

## Plugin Manager

Plugin Manager de FormIt es una única ubicación centralizada en la que puede descubrir y gestionar módulos de extensión.

Plugin Manager se carga automáticamente cuando se inicia FormIt, siempre que este tenga acceso a Internet.

Para acceder a él, haga clic en su icono de ficha![](https://formit3d.github.io/FormItExamplePlugins/docs/images/PluginManagerTab.PNG) ubicado a la derecha de la aplicación:

![](../.gitbook/assets/c1.PNG)

## Categorías de módulos de extensión

Plugin Manager organiza los módulos de extensión en categorías para ayudarle a encontrar aquellos que más le pueden interesar.

![](../.gitbook/assets/d16.png)

**Módulos de extensión instalados:** los módulos de extensión que ha instalado el usuario.&#x20;

**Módulos de extensión recomendados:** módulos de extensión que el equipo de FormIt recomienda para ampliar las funciones principales de FormIt y descubrir nuevos flujos de trabajo. Los módulos de extensión desarrollados por la comunidad aparecen aquí después de que los apruebe el equipo de FormIt.\
Etiqueta de GitHub: _formit-plugin-recommended_

**Módulos de extensión públicos:** módulos creados por la comunidad. El equipo de FormIt no ha revisado ni aprobado los módulos de esta categoría. \
Etiqueta de GitHub: _formit-plugin_

**Para módulos de extensión de desarrolladores**: módulos creados por la comunidad para permitir la creación de nuevos módulos de extensión de FormIt. \
Etiqueta de GitHub: _formit-plugin-developers_

## Añadir el módulo de extensión privado o local

Si está [desarrollando su propio módulo de extensión](how-to-develop-plugins/), puede añadir su dirección URL privada en el campo de la parte inferior del panel y hacer clic en (+), como se muestra a continuación:

![](../.gitbook/assets/d4.PNG)

Para obtener más información sobre cómo añadir el módulo de extensión privado o local, consulte [Vista preliminar de un módulo de extensión en Plugin Manager. ](how-to-develop-plugins/advanced-development/previewing-a-plugin-in-the-plugin-manager.md)

## Restablecimiento de Plugin Manager

Plugin Manager utiliza claves del Registro de Windows para almacenar los repositorios y los módulos instalados. Si necesita restablecer Plugin Manager a sus valores por defecto, elimine la siguiente clave del Registro:

`Computer\HKEY_CURRENT_USER\Software\Autodesk\FormIt 360\Plugins`

⚠️ Nota: Esto desinstalará todos los repositorios y los módulos de extensión añadidos por el usuario, lo que restablecerá Plugin Manager para incluir solo los repositorios y los módulos de extensión integrados.

## Instalación de módulos de extensión

[Plugin Manager](how-to-use-plug-ins.md#plugin-manager) incluye varios módulos de extensión organizados en distintas categorías. Cada módulo de extensión presenta un nombre, una descripción, un vínculo de GitHub y un conmutador de instalación.&#x20;

![](../.gitbook/assets/d5.PNG)

Para instalar un módulo de extensión, simplemente active el conmutador que aparece junto al nombre del módulo.&#x20;

![](../.gitbook/assets/d6.png)

El icono del módulo de extensión seleccionado aparecerá en el panel derecho. Haga clic en él para mostrar la interfaz de usuario del módulo.

![](../.gitbook/assets/d7.PNG)

## Uso de los módulos de extensión

Cada módulo de extensión presenta una interfaz de usuario única definida por su desarrollador. Un módulo suele tener un conjunto de instrucciones sobre cómo utilizarlo, un conjunto de parámetros (cuadros de texto, controles deslizantes, casillas de verificación, etc.) y uno o varios botones para ejecutarlo.

Por ejemplo, utilizaremos uno de los ejemplos más sencillos de Plugin Manager, "Fillet 2D Corners". Cargaremos primero el módulo de extensión desde la sección de módulos recomendados de Plugin Manager. A continuación, mediante las instrucciones proporcionadas por el desarrollador, estableceremos el radio de empalme, seleccionaremos un grupo de caras que empalmar y haremos clic en el botón Fillet Corners.

![](../.gitbook/assets/g4.gif)

##

