---
description: Computational Design in FormIt
---

# FormIt + Dynamo

![](<../.gitbook/assets/20181213 formit + dynamo hero image.png>)

FormIt para Windows incorpora Dynamo para ofrecer flujos de trabajo de diseño computacional excepcionales.

## Novedades de FormIt + Dynamo

### **Gráficos de datos, envío de niveles a Excel y control de facetado**

[FormIt 2023](https://formit.autodesk.com/blog/post/introducing-formit-2023/) permite ejecutar gráficos de Dynamo[ sin un nodo SendToFormIt](formit-+-dynamo.md#graph-types), ofrece la capacidad de [enviar niveles de FormIt a Excel](formit-+-dynamo.md#send-formit-levels-to-excel) y añade el control de [facetado de curvas y superficies mediante los nuevos nodos FormItGroupOptions](../tool-library/curve-+-surface-faceting.md).

### **Entradas de cota y acceso previo a la API de JS**

[FormIt 2022.1](https://formit.autodesk.com/blog/post/introducing-formit-2022-1) aporta la capacidad de utilizar [las cotas conocidas de FormIt como entradas](https://formit.autodesk.com/page/formit-dynamo#dynamo-input-nodes), incluye [opciones de nivel de objeto](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-options-nodes) y ofrece una vista preliminar del [acceso a la API de JavaScript](https://formit.autodesk.com/page/formit-dynamo#dynamo-js-api-nodes). Consígalo [aquí](https://formit.autodesk.com/page/download).

### **Varios nodos SendToFormIt**

[FormIt 2021.3](https://formit.autodesk.com/blog/post/introducing-formit-2021-3) aporta la capacidad de utilizar [varios nodos SendToFormIt y gráficos de Dynamo anidados](https://formit.autodesk.com/page/formit-dynamo#dynamo-groups).

### **Nodo SelectFromFormIt**

[FormIt 2021](https://formit.autodesk.com/blog/post/introducing-formit-2021) añade el nodo [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) y posibilita las sesiones siempre conectadas, la edición de varias instancias y mucho más.

## Para empezar

Obtenga más información sobre la interfaz y vincule los directorios de Dynamo a FormIt.

### **Primera configuración**

¿Es la primera vez que utiliza FormIt + Dynamo? Es posible que deba [configurar primero el sistema](https://formit.autodesk.com/page/formit-dynamo#dynamo-important-notes) para ver el lienzo 3D en Dynamo.

### **Panel de Dynamo**

Utilice el panel de Dynamo para iniciar Dynamo, insertar grupos de Dynamo y editar gráficos de Dynamo:

![Dynamo panel](<../.gitbook/assets/dynamo\_dynamopanel (1).png>)

### **Adición y administración de directorios locales de Dynamo**

* El panel de Dynamo funciona como la [Biblioteca de contenido](https://windows.help.formit.autodesk.com/building-the-farnsworth-house/import-export-and-content-library) y permite vincular y administrar directorios locales que contienen archivos de Dynamo.
* Haga clic en el botón "Vincular directorio" en el panel de Dynamo y, a continuación, haga clic de nuevo en (+) en el cuadro de diálogo Preferencias para seleccionar el directorio que va a vincular a FormIt: <img src="../.gitbook/assets/dynamo_selectdirectory.png" alt="" data-size="line">
* Alterne entre directorios vinculados mediante el menú desplegable:

![](../.gitbook/assets/dynamo\_dropdown.png)

* Solo podrá ver los archivos y las subcarpetas .dyn mediante el panel de Dynamo.
* Utilice la barra de filtros para filtrar los archivos y subcarpetas de Dynamoa fin de encontrar fácilmente lo que necesita:

![](../.gitbook/assets/dynamo\_filter.png)

## Diferentes formas de utilizar Dynamo

Cree y edite gráficos en Dynamo o pruebe parámetros en FormIt sin necesidad de ver el gráfico. O realice ambas acciones a la vez.

### **Tipos de gráfico**

FormIt admite tres tipos de gráficos de Dynamo:

* Gráfico de datos: los gráficos de datos no tienen nodos _SendToFormIt_ y se utilizan para mostrar o pasar datos a través de FormIt. Por ejemplo, puede utilizar gráficos de datos para enviar datos a Excel o calcular datos no geométricos y mostrarlos en un nodo de visualización.
* Gráfico de geometría: estos gráficos generan geometría inmediatamente y se deben colocar en el lienzo para ver sus parámetros. Después de hacer clic en la miniatura, la geometría aparecerá en el cursor para su colocación en la escena 3D. Este gráfico requiere la presencia de al menos un nodo _SendToFormIt_ que reciba geometría al final del gráfico.
* Gráfico de selección: estos gráficos requieren que haya selecciones de FormIt antes de ejecutarse. Aparecerá una solicitud en la esquina superior izquierda de FormIt para indicar qué se debe seleccionar. Después de proporcionar la selección, el gráfico se ejecutará y generará geometría relativa a la selección. Este gráfico requiere la presencia de al menos un nodo _SendToFormIt_ que reciba geometría al final del gráfico.

![](../.gitbook/assets/dynamo-graph-types.png)

### **Gráfico de geometría: inserción de grupos de Dynamo en FormIt**

![](../.gitbook/assets/dynamo\_stairsgif.gif)

* En el panel de Dynamo, haga clic en la miniatura del gráfico de Dynamo que desea ejecutar.
   * Puede utilizar las muestras integradas o [vincular una biblioteca](https://formit.autodesk.com/page/formit-dynamo#dynamo-getting-started) con sus propios archivos de Dynamo.
* Al colocar la geometría en FormIt, se incrusta una copia del gráfico de Dynamo en el archivo FormIt.
   * Para generar geometría, es necesario enlazar un nodo [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) a los nodos de geometría de salida del gráfico.
* La geometría del nodo SendToFormIt estará disponible en el cursor para su inserción.
   * Cuando el gráfico tiene nodos [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) marcados como Es entrada, FormIt solicitará primero la selección (en cada nodo de selección en orden vertical) y, a continuación, generará la geometría en el lugar correcto con respecto a la selección.
* Ahora se incrusta una copia del archivo de Dynamo original en el grupo de FormIt. Esta copia es independiente del gráfico de origen.
* Tras la inserción, el grupo Propiedades se activa automáticamente para mostrar los parámetros disponibles.

### **Gráfico de geometría: modificación de parámetros**

![](../.gitbook/assets/dynamo\_stairsgif2\_modifyparameters.gif)

* Después de insertar un grupo de Dynamo, selecciónelo y cambie al panel Propiedades, o simplemente haga doble clic en el grupo para cambiar automáticamente a Propiedades.
   * Aquí se mostrarán todos los nodos de entrada marcado como "Es entrada" en Dynamo.
   * Los nodos de entrada de [**SelectFromFormIt**](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) se mostrarán como botones en la parte superior y se pueden utilizar para actualizar la selección que se emplea para controlar el gráfico.
   * FormIt admite estos nodos de entrada: controles deslizantes de número, controles deslizantes de enteros, conmutadores booleanos y campos de número o cadena.
* Realice cambios en las entradas de FormIt y, a continuación, haga clic en Ejecutar. El botón Ejecutar cambiará a color azul para indicar que se han modificado los parámetros y que es necesario ejecutar el gráfico.
   * Dynamo se ejecutará en segundo plano para procesar los cambios y devolver la geometría actualizada en FormIt.
   * En FormIt 2022 y versiones posteriores, la primera ejecución desde el panel Propiedades activa un ejemplar de Dynamo dedicado, lo que permite realizar ediciones posteriores con mayor rapidez.
   * Puede seguir utilizando FormIt mientras Dynamo se está ejecutando.&#x20;
* Tenga en cuenta que toda la geometría de cada grupo SendToFormIt se suprimirá y se reemplazará cuando se ejecute el gráfico de Dynamo.

### Gráfico de datos: envío de niveles de FormIt a Excel

En FormIt 2023 y versiones posteriores, puede utilizar Dynamo para enviar niveles de FormIt a Excel:&#x20;

* Descargue el [gráfico de muestra de Dynamo aquí](https://formit-help.s3.amazonaws.com/Send+Levels+to+Excel.dyn).
* Dirija la paleta Dynamo al directorio local en el que se ha guardado el gráfico de Dynamo.
* Haga clic con el botón derecho en la miniatura y seleccione _Editar gráfico incrustado._
* Cree una hoja de cálculo de Excel vacía en algún lugar.
* Edite el campo Ubicación de hoja de cálculo y utilice la ruta de la hoja de cálculo de Excel.
* Edite cualquier otro campo que desee, como Nombre de plano.
* Cierre Dynamo y guarde el gráfico.

Ahora puede hacer clic en el archivo de ejemplo en la paleta y este se ejecutará en FormIt sin necesidad de generar geometría.&#x20;

Verá que las entradas de Dynamo aparecen en la paleta de Dynamo y Excel se abre para mostrar los resultados del gráfico.&#x20;

A medida que realiza cambios en el modelo, puede hacer clic de nuevo en la miniatura del gráfico o en el botón _Ejecutar_ para actualizar la hoja de cálculo con los datos de nivel de la versión más reciente del boceto de FormIt.

![](../.gitbook/assets/dynamo-send-levels-to-excel.gif)

### Iniciar una nueva ventana de Dynamo

![](../.gitbook/assets/dynamo\_launchwindow.gif)

* En FormIt 2021 y versiones posteriores, al hacer clic en el botón Iniciar Dynamo del panel de Dynamo, se inicia automáticamente una sesión conectada con FormIt.
   * De este modo, se abre una plantilla de gráfico en Dynamo y se genera automáticamente la geometría de la plantilla en FormIt.
   * La geometría resultante aparecerá en un grupo nuevo, en el origen del contexto de edición de grupo actual. Es mejor ubicarse en el contexto del grupo deseado antes de iniciar Dynamo.&#x20;
   * La plantilla incluye nodos de FormIt y geometría de ejemplo. Al ajustar los controles deslizantes, se ajustará el tamaño del cubo en ambas aplicaciones.
   * Desde aquí, puede abrir diferentes gráficos de Dynamo o crear un elemento nuevo utilizando estos componentes básicos en la plantilla y guardándolo en otra ubicación mediante la opción Guardar como de Dynamo.

### **Editar gráficos incrustados y de origen**

Los gráficos de Dynamo existentes se pueden editar de dos formas distintas: mediante la edición de los gráficos incrustados que ya se han colocado en FormIt o mediante la edición del gráfico de origen guardado en el equipo.

### **Gráficos incrustados**

Después de colocar un objeto de Dynamo en FormIt, el gráfico subyacente se copia e incrusta en el archivo de FormIt actual. La edición en Dynamo se realiza mediante el botón **Editar gráfico incrustado**.

![](../.gitbook/assets/dynamo\_embeddedgraph.png)

![](../.gitbook/assets/dynamo\_editgraphgif.gif)

* Seleccione el grupo de Dynamo y cambie al panel Propiedades, o simplemente haga doble clic en el grupo para cambiar automáticamente a Propiedades.
* Haga clic en el botón **Editar gráfico incrustado**.
* En Dynamo, observará que ahora aparece "(FormIt)"en el nombre de archivo de la parte superior. Esto significa que está editando un gráfico incrustado en este archivo de FormIt, sin modificar el gráfico de origen.
* Asegúrese de que uno o varios nodos [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) estén conectados a la geometría que desea enviar a FormIt.
* FormIt mostrará las actualizaciones de la geometría en tiempo real a medida que se ajuste el gráfico.
* Si no se guardan los cambios en Dynamo, FormIt volverá a la última versión guardada del gráfico de Dynamo.
* Tenga en cuenta que toda la geometría de cada grupo SendToFormIt se suprimirá y se reemplazará cuando se ejecute el gráfico de Dynamo.

### **Gráficos de origen**

Los gráficos de origen se muestran en el panel de Dynamo después de [vincular los directorios locales](https://formit.autodesk.com/page/formit-dynamo#dynamo-getting-started). Estos gráficos se almacenan en el equipo y se pueden editar en Dynamo haciendo clic en el botón Editar gráfico de origen.

![](../.gitbook/assets/dynamo\_editsourcegraph.png)

![](../.gitbook/assets/dynamo\_sourcegraphgif.gif)

* [Vincule un directorio ](https://formit.autodesk.com/page/formit-dynamo#dynamo-getting-started) que contenga archivos de Dynamo al panel de Dynamo y, a continuación, desplácese a esa ubicación en el panel.&#x20;
* Haga clic con el botón derecho en la miniatura del gráfico de Dynamo que desee editar (o haga clic en la flecha) y seleccione el botón **Editar gráfico de origen**.
* Dynamo se iniciará con el gráfico solicitado abierto y, en FormIt, aparecerá la geometría del resultado final del gráfico.
   * En el caso de los gráficos que utilizan uno o varios nodos [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) como entrada, es posible que no vea la geometría resultante hasta que se realicen las selecciones correspondientes en los nodos SelectFromFormIt.
* La geometría resultante aparecerá en un grupo nuevo, en el origen del contexto de edición de grupo actual.
   * Es mejor ubicarse en el contexto de grupo deseado antes de hacer clic en Editar gráfico de origen.
* Cuando termine de editar, guarde los cambios y cierre Dynamo. En FormIt, el gráfico de origen se habrá copiado e incrustado en el archivo de FormIt.
   * Si necesita realizar más ediciones en el **gráfico de origen**, suprima la copia incrustada y siga estos pasos de nuevo.

### **Facetado de curva de control + superficie**

*  En FormIt 2023 y versiones posteriores, puede controlar el facetado de las curvas y superficies enlazadas a nodos SendToFormIt mediante los nodos FormItGroupOptions, SetCurveFacetingCount y SetSurfaceFacetingCount.

   <img src="../.gitbook/assets/dynamo-formitgroupoptions-faceting-nodes.png" alt="" data-size="original">
* Estos nodos modificarán los parámetros globales de facetado de curvas y superficies, que se definen en Editar -> Preferencias -> Unidades + precisión.
* Esto resulta muy útil si el gráfico de Dynamo debe generar objetos curvos mediante valores de facetado específicos, ya que se reduce la necesidad de cambiar la configuración global de cada gráfico de Dynamo ejecutado en la sesión actual.

![](../.gitbook/assets/dynamo-formitgroupoptions-faceting.gif)

* También puede definir globalmente la configuración de facetado en Editar -> Preferencias -> Unidades + precisión.
* Después de ajustar la calidad de facetado en Preferencias, vuelva a ejecutar el gráfico para utilizar la nueva configuración de facetado global.

![](../.gitbook/assets/dynamo\_controlcurve.gif)

[Obtenga más información sobre los parámetros de facetado de curvas y superficies en FormIt.](https://windows.help.formit.autodesk.com/tool-library/curve-+-surface-faceting)

## Uso de grupos de FormIt con Dynamo

Aproveche los grupos de FormIt para obtener una mejor organización de la geometría de Dynamo y unos flujos de trabajo excepcionales.

### **Grupos y el nodo SelectFromFormIt**

* Al seleccionar la geometría para un nodo [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes), resulta útil almacenar la geometría en un grupo de FormIt y seleccionar el grupo en su lugar.
   * De este modo, tendrá flexibilidad para cambiar el contenido del grupo de FormIt seleccionado y bastará con volver a ejecutar el gráfico que hace referencia al grupo para ver el resultado actualizado.
* Si selecciona geometría desagrupada, los cambios realizados en esa geometría pueden provocar que FormIt solicite que se vuelva a seleccionar la geometría la próxima vez que se ejecute el gráfico.

### **Generación de geometría en grupos**

* Cuando se ejecuta un gráfico de Dynamo en FormIt, sus resultados geométricos se incluyen en un grupo de FormIt.
* Cada nodo [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) del gráfico crea un subgrupo que contiene la geometría del puerto de entrada del nodo.
* Después de generar un objeto de Dynamo en FormIt, todo el gráfico y sus parámetros se incrustan como copia en el archivo de FormIt.
* Cuando se ejecuta el gráfico, se suprime y se regenera la geometría de cada subgrupo.
   * Tenga cuidado al modificar la geometría o pintar superficies dentro de los subgrupos, ya que estos cambios se perderán cuando se vuelva a ejecutar el gráfico de Dynamo.
   * Sin embargo, si pinta subgrupos (y no la geometría que contienen) con materiales de FormIt, dichos materiales se conservarán de una ejecución a otra. Consulte a continuación.

### **Trabajo con grupos y materiales**

* Cuando se utilizan varios nodos **SendToFormIt**, estos se pueden organizar por material, de modo que se puedan pintar distintos subgrupos de FormIt con materiales diferentes.
* En este ejemplo, se genera un edificio completo a partir de planos simples de FormIt. Cada componente de construcción que requiera materiales únicos cuenta con su propio nodo **SendToFormIt**:

![](<../.gitbook/assets/dynamo\_sendtoformit (1).png>)

* Después de aplicar materiales a cada uno de los subgrupos, los materiales se conservan entre las ejecuciones de Dynamo:

![](../.gitbook/assets/dynamo\_materialsgif.gif)

### **Anidación de grupos de Dynamo**

* Puede utilizar el nodo **SelectFromFormIt** para seleccionar los resultados de los subgrupos de un gráfico de Dynamo y controlar los resultados de otro gráfico.&#x20;
* Siguiendo con el ejemplo anterior, la cristalera resultante del gráfico del generador de edificios se utiliza como geometría de selección para el ejemplo de muro cortina/escaparate integrado:

![](../.gitbook/assets/dynamo\_storefront\_curtainwallgif.gif)

* Cuando cambie la forma del edificio, simplemente seleccione el grupo del sistema de montantes y haga clic en Ejecutar en el grupo Propiedades.
   * Aunque el contenido del grupo de cristaleras haya cambiado, el grupo en sí no lo ha hecho, por lo que no es necesario volver a seleccionar la cristalera al ejecutar el gráfico de nuevo.
* El modelo anterior está disponible en FormIt 2022 y versiones posteriores como "Roof Planes Building" en la subcarpeta **Building Masses** de las **muestras de Dynamo**.
* En combinación con las amplias prestaciones de FormIt, Dynamo permite crear y probar un diseño totalmente paramétrico —con materiales y lógica anidada incluidos— en el contexto enriquecido de un potente modelador conceptual:

![](../.gitbook/assets/dynamo\_parametricdesigngif.gif)

### **El comportamiento estándar de los grupos de FormIt sigue aplicándose**

* Aparte de lo que se ha indicado anteriormente, los grupos de Dynamo en FormIt funcionan con las mismas reglas que el resto de grupos. Estas reglas con las siguientes:
   * Al colocar un nuevo objeto de Dynamo desde el panel de Dynamo, se crea un grupo exclusivo que no afecta a ningún ejemplar del mismo objeto que ya se haya colocado en el boceto.
   * Al copiar y pegar grupos de Dynamo, estos se mantienen idénticos. Los cambios realizados en el gráfico de Dynamo de una de las copias también actualizarán la geometría en los ejemplares idénticos, a menos que se establezcan como exclusivos.
   * Puede establecer los grupos de Dynamo como exclusivos con el atajo MU o mediante el menú contextual:

![](<../.gitbook/assets/dynamo\_makeunique (1).png>)

## Nodos fundamentales de FormIt

Los nodos más eficaces para enviar datos entre FormIt y Dynamo.

### **Nodo SendToFormIt**

* Para generar objetos de Dynamo en FormIt, enlace las salidas de nodo geométrico deseadas a la entrada de _geometría_ de al menos un nodo SendToFormIt:

![](<../.gitbook/assets/dynamo\_sendtoformitnode (1).png>)

* FormItGroupOptions es un nuevo puerto (opcional) de FormIt 2022 y se detalla en la sección **Nodos FormItGroupOptions** que encontrará a continuación.
* En FormIt 2021.3 y versiones posteriores, puede utilizar varios nodos SendToFormIt para organizar los resultados de Dynamo en grupos y subgrupos de FormIt.
* [Vea cómo funciona Dynamo con los grupos de FormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-groups).

![](<../.gitbook/assets/dynamo\_sendtoformitnodes (1).png>)

* El nodo SendToFormIt respeta el indicador Es salida, que está activado por defecto. Puede hacer clic con el botón derecho en el nodo para verificarlo:

![](<../.gitbook/assets/dynamo\_isoutput (1).png>)

* Si está activado, la geometría asociada a este nodo SendToFormIt aparecerá en FormIt dentro de un subgrupo.
* Si este indicador está desactivado, no se enviará ninguna geometría a FormIt y se suprimirá el subgrupo correspondiente (si existe).

### **Nodo SelectFromFormIt**

* FormIt 2021 y versiones posteriores ofrece la posibilidad de seleccionar geometría de FormIt para utilizarla en forma de entradas en los gráficos de Dynamo:

![](<../.gitbook/assets/dynamo\_selectfromformitnode (1).png>)

* El nombre asignado al nodo SelectFromFormIt se utilizará en las solicitudes de FormIt. Por tanto, debe ser un nombre que describa el tipo de geometría de FormIt que se ha de seleccionar:

![](<../.gitbook/assets/dynamo\_selectobjectstoarraynode (1).png>)

* Cuando se hace clic en el botón Seleccionar desde FormIt en el editor gráfico de Dynamo o el grupo Propiedades, FormIt inicia un modo de asistente de selección para guiarle a través de la selección de geometría:

![](../.gitbook/assets/dynamo\_selectobjectstoarrayUI.png)

* El nodo SelectFromFormIt respeta el indicador Es entrada, que está activado por defecto. Debe estar activado para que la selección funcione en FormIt. Haga clic con el botón derecho en el nodo para comprobarlo.

![](<../.gitbook/assets/dynamo\_isinput (1).png>)

* Cuando el indicador Es entrada está activado:
   * La miniatura del panel de Dynamo del gráfico indicará que se requiere una selección:

![](../.gitbook/assets/dynamo\_patharray.png)

* Al ejecutar el gráfico, el asistente de selección de FormIt le guiará por la configuración de las selecciones para cada nodo SelectFromFormIt comenzando en la parte superior del gráfico.
* Después de generar elementos por primera vez, verá un botón para cada nodo SelectFromFormIt en el grupo Propiedades de FormIt.

![](../.gitbook/assets/dynamo\_selectarraypath.png)

* Al hacer clic en ellos, se iniciará el asistente de selección para cambiar la selección utilizada para generar la geometría final. El gráfico se volverá a ejecutar automáticamente después de realizar una nueva selección.

### **Consejos, trucos y notas**

* Asigne un nombre al nodo SelectFromFormIt para indicar el tipo de geometría que se espera. Por ejemplo, "Seleccionar contorno de emplazamiento (bordes)".
   * Puede seleccionar cualquier tipo de geometría de FormIt, pero a menudo es mejor restringir la selección a un grupo de FormIt y [seleccionar este grupo en lugar de la geometría original](https://formit.autodesk.com/page/formit-dynamo#dynamo-groups).
* Si necesita mover los resultados de un gráfico de Dynamo basado en la selección, es mejor mover primero la geometría de selección y, a continuación, volver a ejecutar el gráfico, que se ajustará a la geometría de selección actualizada y se reubicará de forma adecuada.&#x20;
   * También puede agrupar los resultados de Dynamo **y** la selección y, a continuación, mover el grupo contenedor.
* Cuando se envía geometría de FormIt a Dynamo, todos los atributos, materiales y grupos anidados se pierden al devolver la geometría a FormIt.
* Si va a editar un gráfico basado en la selección en Dynamo y la geometría seleccionada en FormIt cambia, deberá volver a seleccionar la geometría. Para ello, haga clic en el botón "Seleccionar en FormIt" en el nodo SelectFromFormIt.&#x20;
* Al realizar selecciones en FormIt, se aplica el [filtro de selección](https://windows.help.formit.autodesk.com/tool-library/select-edge-face-or-object#selection-filtering) activo. Por ejemplo, si desea seleccionar vértices de FormIt, deberá activarlos en el filtro de selección.

![](../.gitbook/assets/dynamo\_filterselection.png)

## Otros nodos de entrada

Existe una amplia gama de opciones de entrada para personalizar fácilmente los gráficos de Dynamo en FormIt.

### **Nodo FormItLengthString**

En FormIt 2022.1.0 o posterior, puede utilizar el nodo **FormItLengthString** para especificar cotas en cualquier tipo de unidad de FormIt admitida (pies-pulgada, pulgada, m, cm, mm), independientemente de la configuración de unidades de FormIt en el boceto activo.

![](../.gitbook/assets/dynamo\_formitlengthstring.png)

Al igual que con otros nodos de entrada admitidos, _FormItLengthString_ se mostrará en la paleta Propiedades de FormIt cuando se marque como Es entrada y, cuando se cambie su nombre, su nuevo nombre se mostrará en FormIt:

![](../.gitbook/assets/dynamo\_propertiespalette.png)

Cada ejemplar del nodo _FormItLengthString_ se puede utilizar con cualquier tipo de unidad, por lo que un mismo gráfico de Dynamo podría emplear una combinación de unidades, como se muestra arriba.

### **Cambio de números sin procesar a FormItLengthString**

En FormIt 2022.1.1 y versiones posteriores, al cambiar un gráfico para que utilice nodos FormItLengthString (colocando el primero en un gráfico) o al cambiar un gráfico para que utilice solo números sin procesar (eliminando el último FormItLengthString), se modificarán determinados comportamientos en la edición de gráficos en Dynamo:

* Cuando se utiliza el nodo [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) mientras se edita un gráfico, para cambiar entre los números sin procesar y el nodo _FormItLengthString_ como se ha indicado anteriormente, será necesario volver a seleccionar la geometría de cada nodo _SelectFromFormIt_, de modo que los resultados se sigan adaptando correctamente en FormIt.
* Después de colocar el primer nodo FormItLengthString en un gráfico, todos los números del gráfico destinados a cotas (incluidas las entradas de número sin procesar) indicarán metros (la unidad nativa de Dynamo).
   * El nodo [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) tendrá en cuenta el cambio y garantizará que la geometría generada en FormIt mantiene el tamaño correcto.
   * Por el contrario, al eliminar todos los nodos FormItLengthString del gráfico, los números sin procesar indicarán las unidades establecidas en los parámetros de FormIt (comportamiento anterior).
* La salida numérica de los nodos _FormItLengthString_ también indicará metros, pero esto no cambiará el tamaño de los resultados geométricos en FormIt:

![](<../.gitbook/assets/dynamo\_outputinmeters (1).png>)

### **Otros nodos de entrada admitidos**

Los nodos de entrada estándar de Dynamo se mostrarán en el grupo Propiedades de FormIt cuando se marquen como "Es entrada" en Dynamo:

* Control deslizante de número
* Control deslizante de entero
* Número
* Cadena
* Conmutador booleano

Puede cambiar el nombre de los nodos de entrada (recomendado para mayor claridad) y el nuevo nombre aparecerá en FormIt:

![](<../.gitbook/assets/dynamo\_cuboidsize (1).png>)

![](../.gitbook/assets/dynamo\_inputs.png)

## Otros nodos de salida

Diferentes métodos para mostrar resultados no geométricos de Dynamo en FormIt.

### **Nodo de visualización**

Los nodos de visualización marcados como "Es salida" se mostrarán en la sección "Ver las salidas del nodo" del grupo Propiedades en FormIt 2022 y versiones posteriores:

![](<../.gitbook/assets/dynamo\_watchnodes (1).png>)

### **Mostrar notificaciones de FormIt**

En FormIt 2022.1 o posterior, puede visualizar las notificaciones de FormIt en un gráfico de Dynamo mediante el nodo **UI.ShowNotification**:&#x20;

![](../.gitbook/assets/dynamo\_notifications.png)

### **Iniciar sesión en la consola de FormIt**

En FormIt 2022.1 o posterior, puede registrar datos adicionales directamente en la consola de la aplicación de FormIt (ventana Salida de la secuencia de comandos) con el nodo **FormIt.ConsoleLog**:

![](../.gitbook/assets/dynamo\_logtoconsole.png)

## Nodos de opciones de FormIt

Controle cómo se envían los datos a FormIt, ya sea en el nivel de geometría individual o en el nivel de grupo contenedor.

### **FormItGeometryOptions**

FormIt 2022.1 y versiones posteriores ofrece la posibilidad de personalizar el modo en que se envían las geometrías individuales de Dynamo a FormIt mediante los nodos **FormItGeometryOptions**.

* Especifique la capa de las geometrías individuales dentro del grupo de Dynamo generado.
* Especifique un atributo de cadena para las geometrías individuales dentro del grupo de Dynamo generado.

Los nodos _FormItGeometryOptions_ se pueden utilizar a continuación del nodo _SendToFormIt_:

![](<../.gitbook/assets/dynamo\_formitgeometryoptions (1).png>)

### **FormItGroupOptions**

FormIt 2022 y versiones posteriores ofrece la posibilidad de personalizar el modo en que se genera el grupo de Dynamo del nodo _SendToFormIt_ en FormIt mediante los nodos **FormItGroupOptions**.

* Especifique si el nodo SendToFormIt envía la geometría a FormIt como malla o como objeto.
* Especifique la capa para el grupo creado por el nodo SendToFormIt.
* Especifique un atributo de cadena para el grupo creado por el nodo SendToFormIt.

Puede utilizar cualquier combinación de nodos FormItGroupOptions en cualquier orden encadenándolos en serie:

![](../.gitbook/assets/dynamo\_daisychain.png)

## Nodos de API de JavaScript

FormIt 2022.1 y versiones posteriores ofrecen acceso a las API de JavaScript y a las funciones personalizadas de Dynamo mediante los dos nuevos nodos siguientes:

### **CallJSAPI**

El nodo **CallJSAPI** permite llamar a la API de JavaScript de FormIt directamente desde Dynamo.

![](<../.gitbook/assets/dynamo\_calljsapi (1).png>)

Para obtener información sobre los parámetros y los nombres de función, consulte la documentación de JavaScript que se divide en estas dos partes: [API de FormIt](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_formit.html) y [API WSM](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_wsm.html) (núcleo de modelado).

**CallPluginJS**

Por el contrario, el nodo **CallPluginJS** permite llamar a funciones personalizadas de un módulo de extensión cargado o un fragmento de secuencia de comandos que se ha ejecutado desde la ventana del Editor de secuencias de comandos.

![](<../.gitbook/assets/dynamo\_callpluginjs (1).png>)

## Notas importantes

### **Requisitos del sistema**

* Para utilizar Dynamo en FormIt, se necesita [FormIt para Windows](https://formit.autodesk.com/page/download) v17.0 o posterior.
   * La integración de FormIt + Dynamo añade nuevas funciones y correcciones con regularidad, por lo que siempre es mejor descargar la actualización más reciente cuando esté disponible.
* También es necesario contar con Windows 10. Por razones técnicas, ya no se admiten versiones anteriores de Windows.

**Resolución de problemas**

* Si tiene un sistema con una [tarjeta gráfica NVIDIA o AMD](https://www.howtogeek.com/414201/how-to-check-what-graphics-card-gpu-is-in-your-pc/) o tiene varias tarjetas, es posible que deba configurar FormIt y Dynamo para que utilicen una GPU de alta potencia:
   * _C:/Archivos de programa/Autodesk/FormIt/FormIt.exe_
   * _C:/Archivos de programa/Autodesk/FormIt/DynamoSandbox/FormItDynamoSandbox.exe_
   * Si dispone de una tarjeta NVIDIA, [asegúrese de tener instalado el Panel de control de NVIDIA](https://whatsabyte.com/blog/find-nvidia-control-panel/).
   * Utilice el panel de control de [NVIDIA](https://nvidia.custhelp.com/app/answers/detail/a\_id/2615/\~/how-do-i-customize-optimus-profiles-and-settings%3F) o [AMD](https://www.amd.com/es/support/kb/faq/dh-017) para configurar las siguientes aplicaciones de forma que utilicen la tarjeta gráfica dedicada:
* Si utiliza una configuración regional distinta del inglés, es posible que deba establecer la configuración regional de Windows 10 en inglés para evitar problemas con determinados nodos de Dynamo:
   * Busque "idioma" en Inicio y seleccione "Configuración de idioma".
   * En la parte superior derecha del cuadro de diálogo Idioma, haga clic en "Configuración de idioma administrativo".
   * Haga clic en el botón "Cambiar la configuración regional del sistema...".
   * Elija "Inglés (Estados Unidos)".
* Si algunos gráficos no pueden generar resultados en FormIt al trabajar con geometría o números pequeños, pruebe a cambiar la configuración de escala de Dynamo a "Pequeña":
   * Menú de Dynamo > Preferencias > General > Escala de geometría > Pequeña

![](../.gitbook/assets/dynamo\_geometryscaling.png)

### **Obtener soporte**

¿Necesita ayuda con FormIt + Dynamo? [Háblenos en los foros](https://forums.autodesk.com/t5/formit-forum/bd-p/142?profile.language=es).
