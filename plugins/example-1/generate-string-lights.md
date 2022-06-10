# Generar guirnaldas de luces

_En este capítulo, vamos a probar algunos de los módulos de extensión que se incluyen con FormIt para realizar algunas mejoras en_ _**Encode Campus Sample Model.axm**. Si aún no lo ha hecho, puede descargar el archivo desde el_ [_conjunto de datos de la parte 2 de FormIt Primer_](https://formit-help.s3.amazonaws.com/FormIt+Primer+Part+2+Datasets.zip).

_Este sencillo módulo de extensión permite añadir rápidamente guirnaldas de luces al modelo en función de una línea o una curva._

1 - Antes de añadir nuevas luces, vamos a comprobar el resultado deseado mediante una escena prefabricada en el modelo.

1. Para ir a la escena que contiene las guirnaldas de luces existentes, abra la **paleta Escenas** y haga doble clic en la escena denominada **Eye Level – Short Alley**.
2. Observe las guirnaldas de luces incluidas con este modelo; esto es lo que vamos a recrear, aunque en otro lugar.
3. En la **paleta Capas**, active la capa **Helper Geometry** a fin de ver las líneas originales utilizadas para generar estas guirnaldas de luces.

![](<../../.gitbook/assets/3 (10).png>)

2 - Ahora vayamos a otro callejón y añadamos algunas luces. En la **paleta Escenas**, abra la escena **Eye Level – Long Alley**. Observe que todavía no hay ninguna guirnalda de luces en este callejón.

3 - Para crear una nueva guirnalda de luces, realice lo siguiente:

1. Abra la **paleta Generate String Lights** que acaba de instalar. Para ello, haga clic en el icono de guirnalda de luces. Los iconos de los nuevos módulos de extensión aparecen por defecto en la parte inferior.
2. Cambie la opción **Number of Fixtures** a **10**.
3. Haga doble clic en una de las líneas auxiliares para editar el grupo **String Lights - Long Alley** creado anteriormente. A continuación, haga clic una vez en una de las líneas auxiliares predibujadas para seleccionarla.
4. Haga clic en el botón **Generate String Lights** en la paleta del módulo de extensión; debería aparece una nueva guirnalda de luces. Observe que cada guirnalda de luces se crea como su propio grupo exclusivo.

![](<../../.gitbook/assets/4 (6) (1).png>)

_**Nota:**_ _No pasa nada si algunas de las guirnaldas de luces atraviesan el letrero Groove Coffee porque este módulo de extensión crea una curva catenaria con un pandeo realista debajo del letrero._

4 - Pruebe a crear más guirnaldas de luces mediante el uso de la otra línea auxiliar creada anteriormente o mediante la creación de algunas líneas auxiliares propias. Pruebe con distintos ajustes de la configuración del módulo de extensión para obtener diferentes resultados.

5 - Para mantener organizado el modelo, cuando haya terminado, es recomendable agrupar todas las líneas auxiliares y colocar ese grupo en la capa **Helper Geometry**, así como asignar todos los grupos de guirnaldas de luces a la capa **Context – Exterior Lighting**. Esto impedirá que las líneas auxiliares aparezcan en cualquiera de las escenas de tipo "Eye Level" en la que no deseamos que aparezcan. Cuando termine, los resultados deberían tener un aspecto similar al de la siguiente captura de pantalla.

![](<../../.gitbook/assets/5 (3) (1).png>)

_**Nota:**_ _A diferencia de la geometría creada a partir de una secuencia de comandos de Dynamo, que puede actualizarse y regenerarse mediante la_ _**paleta Propiedades**, los objetos creados por un módulo de extensión son, en su mayoría, geometría normal de FormIt. Una vez creados, solo se pueden editar mediante las herramientas de modelado integradas de FormIt._
