# Creación de versiones

A medida que desarrolla y actualiza el módulo de extensión, es posible que en algún momento deba crear la versión del código.

Por ejemplo, las API de FormIt pueden cambiar entre versiones y, aunque es posible que desee que la nueva versión del módulo de extensión utilice las nuevas API WSM o de FormIt, también desea que el módulo de extensión siga funcionando en clientes anteriores.

A partir de FormIt **v18.0**, puede implementar el control de versiones para el módulo de extensión mediante estos tres sencillos pasos:

* Añada un archivo _versions.json_ a la raíz del directorio de módulos de extensión.
* Especifique cada versión compatible de FormIt y el directorio que contiene esos archivos de módulo de extensión en _versions.json_.
* Utilice el número de versión interno de FormIt (o "Número de compilación") que se encuentra en FormIt en Información > Acerca de.



### Cómo organizar la creación de versiones para el módulo de extensión

Organice los archivos y los directorios del módulo de extensión para que coincidan con _versions.json_.

El archivo _versions.json_ debe presentar el siguiente aspecto:

```
        [
            {
                "version":{
                    "major":18,
                    "minor":0
                },
                "path":"v18_0"
            },
            {
                "version":{
                    "major":19,
                    "minor":1
                },
                "path":"v19_0"
            }
        ]

```

Las rutas anteriores _v18\_0_ y _v19\_0_ deben ser subrutas válidas desde la raíz del directorio o repositorio.

![](../../../.gitbook/assets/i1.png)

![](../../../.gitbook/assets/i2.png)

![](../../../.gitbook/assets/i3.png)

Un buen método para gestionar esto es desplazar el código del módulo de extensión a los subdirectorios. Con el archivo _versions.json_ anterior, una estructura de directorios presentaría este aspecto:

* **versions.json** (archivo)
* **v18\_0** (directorio)

   * **manifest.json** (archivo)
   * **plugin.html** (archivo)
   * **plugin.js** (archivo)


* **v19\_0** (directorio)
   * **manifest.json** (archivo)
   * **plugin.html** (archivo)
   * **plugin.js** (archivo)

Las propiedades opcionales de la versión son "exactVersion" y "lastVersion". "exactVersion" indica que la versión debe coincidir exactamente con la versión de FormIt. "lastVersion" indica la última versión que se puede ejecutar en FormIt.\


```
[
    {
      "version":{
        "major":18,
        "minor":0,
        "exactVersion":true
        },
        "path":"v18_0"
    },
    {
        "version":{
            "major":19,
            "minor":1,
            "lastVersion":true
       },
        "path":"v19_0"
    }
 ]
```

También es posible utilizar ramificaciones/etiquetas/confirmaciones git para las rutas.

Si está trabajando con una versión preliminar o beta de FormIt y desea probar los cambios en un módulo de extensión que solo funciona con la versión preliminar, realice lo siguiente:

* Siga los pasos anteriores, pero cambie el nombre de archivo a _versions\_prerelase.json_.
* Si confirma _versions\_prerelease_ en el repositorio, es posible que desee eliminarlo cuando se publique esa versión preliminar de FormIt.
   * De lo contrario, las versiones preliminares de FormIt cargarán el módulo de extensión desde una ubicación que podría estar obsoleta o destinada a una versión anterior.
