# Módulo de extensión Manage Cameras

_En este capítulo, vamos a probar algunos de los módulos de extensión que se incluyen con FormIt para realizar algunas mejoras en_ _**Encode Campus Sample Model.axm**. Si aún no lo ha hecho, puede descargar el archivo desde el_ [_conjunto de datos de la parte 2 de FormIt Primer_](https://formit-help.s3.amazonaws.com/FormIt+Primer+Part+2+Datasets.zip).

A lo largo de FormIt Primer, hemos utilizado escenas como herramientas valiosas para desplazarnos por el modelo y controlar su visibilidad. Este módulo nos permite ver y editar la elevación de la cámara actual, exportar cámaras para cada escena como objetos 3D y copiar estas escenas entre modelos.

1 - En primer lugar, ajustaremos la escena **Eye Level – Long Alley** para que su cámara se encuentre a la altura de los ojos:

1. Si aún no lo ha hecho, regrese a la escena **Eye Level – Long Alley**. Para ello, haga doble clic en la **paleta Escenas**.
2. Abra la **paleta Manage Cameras**. Para ello, haga clic en la cámara con un icono de engranaje.
3. Cambie el valor de **Height Above Ground** a **5'-8"**.

![](<../../.gitbook/assets/6 (6) (1).png>)

_**Nota:**_ _Si el modelo tiene niveles, este módulo de extensión también mostrará la altura sobre el nivel más cercano por debajo de la_ _**cámara principal**._

2 - A continuación, realice lo siguiente:

1. Regrese a la **paleta Escenas**.
2. Asegúrese de que la escena **Eye Level – Long Alley** esté aún seleccionada (de lo contrario, haga clic una vez en ella para seleccionarla).
3. Haga clic en el botón **Actualizar escena** para guardar la nueva altura de la cámara en esta escena.

![](<../../.gitbook/assets/7 (1) (1).png>)

_**Nota:**_ _También se puede ajustar el ángulo y la posición de la cámara de una escena activando o desactivando el botón_ _**Editar cámaras de escena**_ _en la parte superior de la_ _**paleta Escenas**_ _(entre los botones de actualización y reproducción)._

3 - A continuación, exportemos nuestras escenas a un nuevo modelo. Debemos crear primero los objetos de cámara para todas las escenas con el módulo de extensión **Manage Cameras**:

1. Vuelva a abrir la **paleta Manage Cameras**.
2. Asegúrese de que la opción **Copy Cameras to Clipboard** esté activada.
3. Haga clic en el botón **Export Scenes to Cameras**. Este proceso puede tardar unos segundos en completarse.
4. Si todo el lienzo se ha vuelto blanco, es porque la **cámara principal** se ha alineado con una de las cámaras de la escena. **Utilice la herramienta Zoom (Z)** para reducir la vista hasta que pueda ver los tres edificios principales y los objetos de cámara recién creados. Tenga en cuenta que los objetos de cámara se colocan automáticamente en un grupo de gran tamaño denominado **Cameras**. En ese grupo, cada cámara individual se coloca en su propio grupo con el mismo nombre que las escenas a partir de las que se ha creado.

![](<../../.gitbook/assets/8 (7) (1).png>)

4 - Vamos a copiar estas escenas en un nuevo modelo. Dado que los datos de la cámara se han guardado en el portapapeles, solo tenemos que realizar lo siguiente:

1. **Guarde** **(Ctrl + S)** el modelo actual y ciérrelo.
2. Inicie un nuevo boceto vacío. Para ello, seleccione **Nuevo boceto (Ctrl + N)** en el menú desplegable **Archivo** de la barra de **Menú principal**.
3. Si aún no lo ha hecho, abra el módulo de extensión **Manage Cameras** y asegúrese de que esté seleccionada la opción **Look for Cameras on Clipboard**.
4. Haga clic en el botón **Importar escenas de cámaras** situado cerca de la parte inferior del módulo de extensión; se importarán las escenas del otro modelo. Para comprobarlo, abra la **paleta Escenas** o active la capa **Camera**. Verá que todas las escenas y los objetos de cámara 3D se han importado a este modelo.

![](<../../.gitbook/assets/9 (7) (1).png>)
