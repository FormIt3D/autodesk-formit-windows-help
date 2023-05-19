# 3D Context Creator 

![](<../../.gitbook/assets/3D Context Creator_new.gif>)

## ¿Qué es?

3D Context Creator es un módulo de extensión fácil de usar que generará edificios con contexto 3D dentro de FormIt. 

Este módulo de extensión le ayuda a visualizar el emplazamiento del proyecto con su contexto circundante y a tomar decisiones fundamentadas en las primeras fases del proceso de diseño.

Este módulo de extensión recupera datos de [Open Street Map](https://www.openstreetmap.org/about) para transformarlos en geometrías de FormIt. El código fuente de este módulo de extensión está disponible en [Github](https://github.com/matterlab-co/FormIt-Context-Plugin).

## ¿Cómo usarlo?

Para instalarlo, simplemente active el conmutador del módulo de extensión desde Plugin Manager, como lo haría con cualquier otro módulo.

![](../../.gitbook/assets/contextcreator3.png)

Una vez activado, el módulo de extensión debe aparecer en el lado derecho de la aplicación y estar listo para su uso.

![](<../../.gitbook/assets/3D Context Creator new_no location (1).png>)

Si el emplazamiento aún no tiene una ubicación, puede hacer clic en el vínculo **Set Location...** para establecer una ubicación y definir el contorno que se utilizará para generar el contexto 3D.

Una vez que haya definido la ubicación, 3D Context Creator se actualizará con la ubicación actual y el botón se activará:

![](<../../.gitbook/assets/3D Context Creator new_with location.png>)

3D Context Creator simplemente utilizará la extensión de la imagen de satélite para generar el contexto 3D. Solo tiene que hacer clic en **Generate 3D Context**.

En función de la extensión de la imagen de satélite y de la complejidad de los edificios, el contexto puede tardar algunos segundos en generarse.

Los edificios con contexto 3D se colocarán automáticamente en un ejemplar de grupo y se insertarán en una capa denominada "Context Buildings". Puede activar y desactivar la visibilidad del contexto mediante esta capa.

![](<../../.gitbook/assets/3D Context Creator_layers.png>)

![](<../../.gitbook/assets/3D Context Creator_NYC.png>)

Si más adelante decide cambiar la ubicación o ajustar el alcance de la imagen de satélite, puede hacer clic de nuevo en **Generate 3D Context** para volver a generar los edificios. 

_Tenga en cuenta que, al volver a generar el contexto, se reemplazará el ejemplar de grupo que contiene los edificios por un nuevo ejemplar, por lo que se perderán los cambios realizados en los edificios._ Para evitar esto, puede desagrupar el contenedor de contexto y, a continuación, volver a agruparlo.

## **Algunos ejemplos**

Intente adivinar las ciudades icónicas que se representan en los siguientes contextos:

![](<../../.gitbook/assets/image (2) (1).png>)

![](<../../.gitbook/assets/image (34).png>)

![](<../../.gitbook/assets/image (13) (1) (1).png>)

![](<../../.gitbook/assets/image (59).png>)
