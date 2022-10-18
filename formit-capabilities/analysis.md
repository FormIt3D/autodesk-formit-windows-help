---
descripción: >- Inicie un flujo de trabajo de BIM mediante la evaluación del rendimiento de los elementos desde el principio del proceso de diseño.
---

# Análisis solar + energético

\![](<../.gitbook/assets/20220317 Solar Analysis.png>)

## Análisis energético en FormIt

Analice la eficiencia energética del modelo de construcción en las primeras fases del proceso de diseño.

[Vea sus proyectos de Insight](https://gbs.autodesk.com/OneEnergy/Insight)

## Análisis energético con Insight

Con una suscripción a **FormIt Pro** a través de la [AEC Collection](https://www.autodesk.com/collections/architecture-engineering-construction/overview), tiene acceso a Análisis energético con **Insight:**

* Analice modelos de diseño en las fases iniciales con el motor de análisis de Green Building Studio.
* Conéctese a una vista de panel de los resultados del análisis para comparar las opciones del diseño.
* Ajuste los widgets de factor de análisis energético, como Window to Wall Ratio, Building Orientation, etc.
* Resuma el impacto energético del edificio con un único número calculado como coste base por área.
* Guarde los resultados del análisis energético para revisarlo posteriormente con clientes y otras partes interesadas.

## Novedades de FormIt + Insight<a href="#insight-what-s-new" id="insight-what-s-new"></a>

### **Mejoras en la fiabilidad de Insight**<a href="#improvements-to-insight-reliability" id="improvements-to-insight-reliability"></a>

* [FormIt 2021](https://formit.autodesk.com/blog/post/introducing-formit-2021) ahora comprueba si el modelo presenta problemas comunes antes de iniciar Insight y repara los errores habituales de Insight para ofrecer una experiencia más fiable.
* FormIt 2021 también mejora la fiabilidad general de la conexión FormIt + Insight, ya que aborda muchos errores conocidos y mejora las tasas de éxito de las ejecuciones.

## Para empezar<a href="#insight-getting-started" id="insight-getting-started"></a>

### **Cómo funciona** <a href="#how-it-works" id="how-it-works"></a>

* El análisis energético de Insight carga los datos del modelo de FormIt y ejecuta varios cientos de análisis en la nube para determinar distintas calificaciones energéticas.
* El análisis energético utiliza Revit para analizar el modelo, por lo que, al igual que al enviar datos de FormIt a Revit, deberá [asegurarse de que el modelo de FormIt sea hermético y múltiple](https://formit.autodesk.com/blog/post/repairing-solid-models).

### **Preparación del modelo de FormIt** <a href="#preparing-your-formit-model" id="preparing-your-formit-model"></a>

* Insight utilizará cualquier geometría visible en el boceto de FormIt.
  * Asegúrese de que la funda de construcción que desea analizar es la única geometría visible.
  * Coloque la geometría de soporte, como los elementos de entorno, mobiliario y emplazamiento, en una [capa](../tool-library/layers.md) independiente y desactive la capa.
* Insight funciona mejor con un modelo de construcción sólido y sencillo.
  * Asegúrese de que la masa de construcción sea [sólida y hermética](https://formit.autodesk.com/blog/post/repairing-solid-models).
  * Si el diseño de construcción ya tiene huecos para ventanas y puertas, es mejor crear una nueva masa sin huecos específicamente para el análisis energético y ocultar la versión más detallada mediante las capas.
* La masa de construcción simple debe tener [niveles](../tool-library/levels-and-area.md) aplicados.
* El modelo de FormIt debe tener definida una [ubicación](../tool-library/setting-location.md).

![](../.gitbook/assets/insight.png)

### **Inicio del análisis energético** <a href="#starting-energy-analysis" id="starting-energy-analysis"></a>

* Busque el botón de análisis energético en la barra de herramientas.

![](../.gitbook/assets/generate\_insight.png)

* Haga clic en "Generar información" para iniciar el proceso.
* Se cargarán los datos de modelo visibles y se ejecutarán varios cientos de simulaciones en la nube.
* Cuando el proceso finalice, aparecerá un mensaje en la parte superior de la pantalla y el menú se actualizará para indicar que hay una nueva información lista para su visualización.
  * Haga clic en "Ver información" para ver el análisis en el navegador web.
  * También puede encontrar todas la información en [Autodesk Insight](https://gbs.autodesk.com/OneEnergy/Insight).

## Resolución de problemas<a href="#insight-troubleshooting" id="insight-troubleshooting"></a>

### **Errores frecuentes** <a href="#common-errors" id="common-errors"></a>

* "No se ha podido crear el proyecto de Insight. Inténtelo de nuevo más tarde".
  * Inicie sesión en el [centro de controles de Green Building Studio](https://gbs.autodesk.com/GBS/Project) y, a continuación, reinicie FormIt.
    * Si no puede iniciar sesión o si aparece una página de "acceso denegado", es posible que deba [adquirir una suscripción a Green Building Studio](https://knowledge.autodesk.com/search-result/caas/CloudHelp/cloudhelp/ENU/BPA-Help/files/GUID-7FCFF904-F943-4020-BF7F-53AA7148673D-htm.html).
  * Compruebe que el modelo sea [sólido y hermético](https://formit.autodesk.com/blog/post/repairing-solid-models).
  * Compruebe si hay problemas con los servicios de FormIt en el [Centro de controles de estado de Autodesk](https://health.autodesk.com/).
* Para comprobar si Green Building Studio ha ejecutado correctamente los análisis energéticos para este proyecto, consulte el panel principal de [Green Building Studio](https://gbs.autodesk.com/GBS/Project).
  * El último proyecto debe aparecer en la parte superior de la lista y debe mostrar 248 ejecuciones.
  * Si muestra 0 ejecuciones, [infórmenos en los foros de FormIt](https://forums.autodesk.com/t5/formit-forum/bd-p/142) y le ayudaremos a solucionar el problema.

### **Registros detallados** <a href="#detailed-logs" id="detailed-logs"></a>

* La versión web de FormIt proporciona detalles adicionales cuando se producen errores en el análisis energético:
  * Vaya a [FormIt Web](https://formit.autodesk.com/app).
  * Abra el modelo que presenta problemas con el análisis energético.
  * Ejecute el análisis energético.
  * Abra las herramientas para desarrolladores (pulse F12 en Google Chrome o Firefox).
  * Consulte la ficha Consola.
  * Copie los errores o realice una captura de pantalla de los mismos e [informe de ellos en los foros de FormIt](https://forums.autodesk.com/t5/formit-forum/bd-p/142).

## Análisis solar

Con una suscripción a **FormIt Pro** a través de la [AEC Collection](https://www.autodesk.com/collections/architecture-engineering-construction/overview), puede visualizar el impacto del sol en el edificio:

* Especifique las caras pertinentes para el análisis de efectos del sol.
* Visualice los resultados en segundos en el lienzo de la aplicación.
* Coloque el cursor sobre un punto de entrada para ver valores calculados específicos de los efectos del sol.
* Elija ver los resultados como un estudio de cristalera mensual o como un estudio de viabilidad anual de los paneles solares.

Obtenga más información sobre el [análisis solar](../tool-library/solar-analysis.md) en FormIt Pro.
