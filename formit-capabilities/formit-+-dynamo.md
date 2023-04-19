---
description: Computational Design in FormIt
---

# FormIt + Dynamo

![](<../.gitbook/assets/20181213 formit + dynamo hero image.png>)

FormIt para Windows incorpora Dynamo para ofrecer flujos de trabajo de diseño computacional excepcionales.

## Novedades de FormIt + Dynamo

FormIt 2024 se ha actualizado con la versión 2.17 de Dynamo más reciente.

### **Gráficos de datos, envío de niveles a Excel y control de facetado**

[FormIt 2023](https://formit.autodesk.com/blog/post/introducing-formit-2023/) permite ejecutar gráficos[ de Dynamo sin un nodo SendToFormIt](formit-+-dynamo.md#graph-types), ofrece la capacidad de [enviar niveles de FormIt a Excel](formit-+-dynamo.md#send-formit-levels-to-excel) y añade el control de [facetado de curvas y superficies mediante los nuevos nodos FormItGroupOptions](../tool-library/curve-+-surface-faceting.md).

### **Entradas de cota y acceso previo a la API de JS**

[FormIt 2022.1](https://formit.autodesk.com/blog/post/introducing-formit-2022-1) permite utilizar [cotas de FormIt conocidas como entradas](https://formit.autodesk.com/page/formit-dynamo#dynamo-input-nodes), presenta [opciones de nivel de objeto](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-options-nodes) y ofrece una vista preliminar del [acceso a la API de JavaScript](https://formit.autodesk.com/page/formit-dynamo#dynamo-js-api-nodes). Consiga esta versión [aquí](https://formit.autodesk.com/page/download).

### **Varios nodos SendToFormIt**

[FormIt 2021.3](https://formit.autodesk.com/blog/post/introducing-formit-2021-3) permite utilizar [varios nodos SendToFormIt y gráficos de Dynamo anidados](https://formit.autodesk.com/page/formit-dynamo#dynamo-groups).

### **Nodo SelectFromFormIt**

[FormIt 2021](https://formit.autodesk.com/blog/post/introducing-formit-2021) añade el nodo [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) y permite las sesiones con conexión permanente, la edición de varios ejemplares y mucho más.

## Para empezar

Obtenga más información sobre la interfaz y vincule los directorios de Dynamo a FormIt.

### **Primera configuración**

¿Es la primera vez que utiliza FormIt + Dynamo? Es posible que deba [configurar el sistema](https://formit.autodesk.com/page/formit-dynamo#dynamo-important-notes) primero para ver el lienzo 3D en Dynamo.

### **Panel de Dynamo**

Utilice el panel de Dynamo para iniciar Dynamo, insertar grupos de esta solución y editar sus gráficos:

![Panel de Dynamo](<../.gitbook/assets/dynamo_dynamopanel (1).png>)

### **Adición y administración de directorios locales de Dynamo**

* El panel de Dynamo funciona como la [biblioteca de contenido](https://windows.help.formit.autodesk.com/building-the-farnsworth-house/import-export-and-content-library), lo que permite vincular y administrar directorios locales que contienen archivos de Dynamo.
* Haga clic en el botón "Vincular directorio" en el panel de Dynamo y, a continuación, haga clic de nuevo en (+) en el cuadro de diálogo Preferencias para seleccionar el directorio que va a vincular a FormIt: <img src="../.gitbook/assets/dynamo_selectdirectory.png" alt="" data-size="line">
* Alterne entre directorios vinculados mediante el menú desplegable:

![](../.gitbook/assets/dynamo\_dropdown.png)

* Solo podrá ver los archivos y las subcarpetas .dyn mediante el panel de Dynamo.
* Utilice la barra de filtros para filtrar los archivos y subcarpetas de Dynamo a fin de encontrar fácilmente lo que necesita:

![](../.gitbook/assets/dynamo\_filter.png)

## Diferentes formas de utilizar Dynamo

Cree y edite gráficos en Dynamo o pruebe parámetros en FormIt sin necesidad de ver el gráfico. O realice ambas acciones a la vez.

### **Tipos de gráfico**

FormIt admite tres tipos de gráficos de Dynamo:

* Gráfico de datos: los gráficos de datos no tienen nodos _SendToFormIt_ y se utilizan para visualizar o transferir datos a través de FormIt. Por ejemplo, puede utilizar gráficos de datos para enviar datos a Excel o calcular datos no geométricos y mostrarlos en un nodo de visualización.
* Gráfico de geometría: estos gráficos generan geometría inmediatamente y se deben colocar en el lienzo para ver sus parámetros. Después de hacer clic en la miniatura, la geometría aparecerá en el cursor para su colocación en la escena 3D. Este gráfico requiere la presencia de al menos un nodo _SendToFormIt_ que reciba geometría al final del gráfico.
* Gráfico de selección: estos gráficos requieren que haya selecciones de FormIt antes de ejecutarse. Aparecerá una solicitud en la esquina superior izquierda de FormIt para indicar qué se debe seleccionar. Después de proporcionar la selección, el gráfico se ejecutará y generará geometría relativa a la selección. Este gráfico requiere la presencia de al menos un nodo _SendToFormIt_ que reciba geometría al final del gráfico.

![](../.gitbook/assets/dynamo-graph-types.png)

### **Gráfico de geometría: inserción de grupos de Dynamo en FormIt**

![](../.gitbook/assets/dynamo\_stairsgif.gif)

* En el panel de Dynamo, haga clic en la miniatura del gráfico de Dynamo que desea ejecutar.
  * Puede utilizar las muestras integradas o [vincular una biblioteca](https://formit.autodesk.com/page/formit-dynamo#dynamo-getting-started) de sus propios archivos de Dynamo.
* Al colocar la geometría en FormIt, se incrusta una copia del gráfico de Dynamo en el archivo de FormIt.
  * Para generar geometría, es necesario enlazar un nodo [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) a los nodos de geometría de salida del gráfico.
* La geometría del nodo SendToFormIt estará disponible en el cursor para su inserción.
  * Cuando el gráfico tiene nodos [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) marcados como Es entrada, FormIt solicitará primero la selección (en cada nodo de selección en orden vertical) y, a continuación, generará la geometría en el lugar correcto con respecto a la selección.
* Ahora se incrusta una copia del archivo de Dynamo original en el grupo de FormIt. Esta copia es independiente del gráfico de origen.
* Tras la inserción, el grupo Propiedades se activa automáticamente para mostrar los parámetros disponibles.

### **Gráfico de geometría: modificación de parámetros**

![](../.gitbook/assets/dynamo\_stairsgif2\_modifyparameters.gif)

* Después de insertar un grupo de Dynamo, selecciónelo y cambie al panel Propiedades, o simplemente haga doble clic en el grupo para cambiar automáticamente a Propiedades.
  * Aquí se mostrarán todos los nodos de entrada marcados como "Es entrada" en Dynamo.
  * Los nodos de entrada de [**SelectFromFormIt**](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) se mostrarán como botones en la parte superior y se pueden utilizar para actualizar la selección que se emplea para controlar el gráfico.
  * FormIt admite estos nodos de entrada: controles deslizantes de número, controles deslizantes de enteros, conmutadores booleanos y campos de número o cadena.
* Realice cambios en las entradas de FormIt y, a continuación, haga clic en Ejecutar. El botón Ejecutar cambiará a color azul para indicar que se han modificado los parámetros y que es necesario ejecutar el gráfico.
  * Dynamo se ejecutará en segundo plano para procesar los cambios y devolver la geometría actualizada en FormIt.
  * En FormIt 2022 y versiones posteriores, la primera ejecución desde el panel Propiedades activa un ejemplar de Dynamo dedicado, lo que permite realizar ediciones posteriores con mayor rapidez.
  * Puede seguir utilizando FormIt mientras Dynamo se está ejecutando. 
* Tenga en cuenta que toda la geometría de cada grupo SendToFormIt se suprimirá y se reemplazará cuando se ejecute el gráfico de Dynamo.

### Gráfico de datos: envío de niveles de FormIt a Excel

En FormIt 2023 y versiones posteriores, puede utilizar Dynamo para enviar niveles de FormIt a Excel: 

* Descargue el [gráfico de muestra de Dynamo aquí](https://formit-help.s3.amazonaws.com/Send+Levels+to+Excel.dyn).
* Dirija la paleta Dynamo al directorio local en el que se ha guardado el gráfico de Dynamo.
* Haga clic con el botón derecho en la miniatura y seleccione _Editar gráfico incrustado_.
* Cree una hoja de cálculo de Excel vacía en la ubicación que desee.
* Edite el campo Ubicación de hoja de cálculo y utilice la ruta de la hoja de cálculo de Excel.
* Edite cualquier otro campo que desee, como Nombre de plano.
* Cierre Dynamo y guarde el gráfico.

Ahora puede hacer clic en el archivo de ejemplo en la paleta y este se ejecutará en FormIt sin necesidad de generar geometría. 

Verá que las entradas de Dynamo aparecen en la paleta de Dynamo y Excel se abre para mostrar los resultados del gráfico. 

A medida que realiza cambios en el modelo, puede hacer clic de nuevo en la miniatura del gráfico o en el botón _Ejecutar_ para actualizar la hoja de cálculo con los datos de nivel de la versión más reciente del boceto de FormIt.

![](../.gitbook/assets/dynamo-send-levels-to-excel.gif)

### Iniciar una nueva ventana de Dynamo

![](../.gitbook/assets/dynamo\_launchwindow.gif)

* En FormIt 2021 y versiones posteriores, al hacer clic en el botón Iniciar Dynamo del panel de Dynamo, se inicia automáticamente una sesión conectada con FormIt.
  * De este modo, se abre una plantilla de gráfico en Dynamo y se genera automáticamente la geometría de la plantilla en FormIt.
  * La geometría resultante aparecerá en un grupo nuevo, en el origen del contexto de edición de grupo actual. Es mejor ubicarse en el contexto del grupo deseado antes de iniciar Dynamo. 
  * La plantilla incluye nodos de FormIt y geometría de ejemplo. Al ajustar los controles deslizantes, se ajustará el tamaño del cubo en ambas aplicaciones.
  * Desde aquí, puede abrir diferentes gráficos de Dynamo o crear un elemento nuevo utilizando estos componentes básicos en la plantilla y guardándolo en otra ubicación mediante la opción Guardar como de Dynamo.

### **Editar gráficos incrustados y de origen**

Los gráficos de Dynamo existentes se pueden editar de estas dos formas: mediante la edición de los gráficos incrustados que ya se han colocado en FormIt o mediante la edición del gráfico de origen guardado en el equipo.

### **Gráficos incrustados**

Después de colocar un objeto de Dynamo en FormIt, el gráfico subyacente se copia y se incrusta en el archivo de FormIt actual. La edición en Dynamo se realiza mediante el botón **Editar gráfico incrustado**.

![](../.gitbook/assets/dynamo\_embeddedgraph.png)

![](../.gitbook/assets/dynamo\_editgraphgif.gif)

* Seleccione el grupo de Dynamo y cambie al panel Propiedades, o simplemente haga doble clic en el grupo para cambiar automáticamente a Propiedades.
* Haga clic en el botón **Editar gráfico incrustado**.
* En Dynamo, observará que ahora aparece "(FormIt)" en el nombre de archivo de la parte superior. Esto significa que está editando un gráfico incrustado en este archivo de FormIt, sin modificar el gráfico de origen.
* Asegúrese de que uno o varios nodos [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) estén conectados a la geometría que desea enviar a FormIt.
* FormIt mostrará las actualizaciones de la geometría en tiempo real a medida que se ajuste el gráfico.
* Si no se guardan los cambios en Dynamo, FormIt volverá a la última versión guardada del gráfico de Dynamo.
* Tenga en cuenta que toda la geometría de cada grupo SendToFormIt se suprimirá y se reemplazará cuando se ejecute el gráfico de Dynamo.

### **Gráficos de origen**

Los gráficos de origen se muestran en el panel de Dynamo después de [vincular directorios locales](https://formit.autodesk.com/page/formit-dynamo#dynamo-getting-started). Estos gráficos se almacenan en el equipo y se pueden editar en Dynamo. Para ello, haga clic en el botón Editar gráfico de origen.

![](../.gitbook/assets/dynamo\_editsourcegraph.png)

![](../.gitbook/assets/dynamo\_sourcegraphgif.gif)

* [Vincule un
