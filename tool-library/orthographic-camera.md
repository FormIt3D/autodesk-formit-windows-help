# Cámara ortogonal y en perspectiva

FormIt 2023 incluye varias opciones de cámara ortogonal y en perspectiva. Puede encontrar los botones Ortogonal, Perspectiva de dos puntos y Perspectiva de tres puntos en el menú de navegación flotante:

![Botones de vista de cámara de perspectiva de tres puntos (superior), perspectiva de dos puntos (medio) y ortogonal (inferior)](../.gitbook/assets/camera-2point-floating-nav-blurred.png)

### Perspectiva de tres puntos

* Esta es la cámara de perspectiva predeterminada. En determinados ángulos de cámara, las líneas verticales parecen converger cerca de la parte superior de la cámara.
* La posición de la cámara definida en este modo definirá el plano delimitador de la cámara ortogonal.
* Al utilizar Ctrl + zoom en este modo, se aplica zoom a una velocidad constante, sin ralentizar la vista a medida que la cámara se aproxima a los objetos.

### Perspectiva de dos puntos

* Esta cámara es similar a la perspectiva de 3 puntos, pero garantiza que las líneas verticales permanezcan en vertical.
* En determinados ángulos de cámara, la geometría puede aparecer distorsionada para mantener las líneas verticales en vertical en todo momento.
* La posición de la cámara definida en este modo definirá el plano delimitador de la cámara ortogonal.
* Al utilizar Ctrl + zoom en este modo, se aplica zoom a una velocidad constante, sin ralentizar la vista a medida que la cámara se aproxima a los objetos.
* La perspectiva de dos puntos también es un modo de trabajo, por lo que observará que las líneas verticales permanecen en vertical incluso cuando la cámara cambia, lo que puede distorsionar la escena en determinados ángulos de cámara.

![](../.gitbook/assets/camera-2point-working-mode.gif)

### Ortogonal

* Un modo de proyección ortogonal útil para diagramas, dibujos de detalle 3D y otros gráficos sin perspectiva.
* La posición de la cámara definida en cualquiera de los dos modos de perspectiva define el plano delimitador de la cámara ortogonal. Si ve que la escena se recorta de forma inesperada, cambie a un modo de perspectiva, reduzca la vista y, a continuación, vuelva al modo ortogonal.

### Uso de los modos

Todos los modos de cámara son modos de trabajo completos con acceso a las herramientas de navegación y dibujo. El menú permite alternar fácilmente entre las distintas cámaras.&#x20;

![Cambio entre los tres modos de cámara: perspectiva de tres puntos, perspectiva de dos puntos y ortogonal.](../.gitbook/assets/perspective-gif.gif)

Una vez que haya seleccionado una cámara, todas las demás herramientas de cámara respetarán el modo actual. Por ejemplo, **Alinear cámara con cara** alineará la cámara ortogonal con la cara, lo que dará como resultado una vista de elevación ortogonal.

Si se desplaza manualmente a una vista ortogonal predefinida, como Vista superior o Vista frontal, la cámara ortogonal se ajustará a esa posición, lo que facilitará el acceso a esas vistas predefinidas.

![](../.gitbook/assets/orthoorienttoface.gif)
