# Módulo de extensión Properties Plus

_Este módulo de extensión es una versión con más funciones de la_ _**paleta Propiedades**. Si selecciona varios grupos o tipos de geometría, este módulo de extensión le proporcionará un desglose de lo que se ha seleccionado, además de permitir el cambio de nombre masivo de grupos y ejemplares de grupo._

1 **-** Veremos primero las propiedades de un grupo de puertas en el modelo base. Vuelva a abrir **Encode Campus Sample Model.axm** y regrese a la escena **Eye Level - Long Alley**. Para comenzar a utilizar el módulo de extensión **Properties Plus**, realice lo siguiente:

1. Abra la **paleta Properties Plus**. Para ello, haga clic en la propiedad con un signo más.
2. Asegúrese de que la opción **Actualizar al cambiar la selección** esté seleccionada.
3. Seleccione uno de los grupos de puertas de cristal dobles denominado **Door** en el lado derecho del callejón.
4. En el área **Selection Count**, la opción **Total Objects** nos indica que hay un (**1**) objeto seleccionado.
5. Justo debajo, podemos encontrar más información sobre los tipos de objetos que se han seleccionado. En este caso, hay un (**1**) grupo seleccionado y este tiene cuatro (**4**) ejemplares en alguna parte del modelo.

![](<../../.gitbook/assets/10 (2) (1).png>)

_**Nota:**_ _Comprobar el número de ejemplares del grupo seleccionado puede ser muy útil para evitar que se modifiquen accidentalmente varios elementos cuando en realidad solo se desea cambiar el elemento seleccionado, pero se ha olvidado establecerlo primero como exclusivo._

2 - Este módulo de expansión nos permite editar el nombre de un grupo o un ejemplar de grupo sin necesidad de pasar al modo de edición de grupo y cambiar el nombre de varios ejemplares a la vez. Como hemos aprendido anteriormente, cada grupo tiene un nombre, pero cada ejemplar de ese grupo también puede tener un nombre de "ejemplar" exclusivo. Como es probable que haya muchos tipos de puertas en este modelo, deseamos asignar a este grupo y algunas de sus instancias nombres más específicos.

1. Con el primer grupo de **puertas** de cristal seleccionado, añada otro grupo de **puertas** a la selección actual. Para ello, mantenga pulsada la tecla **Mayús** o **Ctrl** y haga clic una vez en el otro grupo de **puertas** de cristal dobles cerca del primero.
2. Observe que ahora, la **paleta Properties Plus** ha actualizado el valor de **Selection Count** para mostrar que hay dos (**2**) ejemplares seleccionados, pero aún solo una (**1**) única **familia** (también conocido como grupo) seleccionada. (Aunque este módulo de extensión utilice el término **Familia**, que debería ser conocido para los usuarios de Revit, en este contexto, significa lo mismo que un grupo de FormIt).
3. En el área **Group Family**, actualice el campo **Name** para que sea **Doors – Double Glass Storefront**. De este modo, se actualizará el nombre del grupo para todos los ejemplares, independientemente de dónde se encuentren o de si están seleccionados actualmente, sin necesidad de hacer doble clic y editar el grupo.
4. Dado que estos dos ejemplares son puertas de acceso al área de Groove Coffee, cambiemos el nombre de estos dos ejemplares introduciendo **Groove Coffee Door** en el campo **Name** del área **Multiple Group Instances**.

**Nota:** En la **paleta Propiedades** estándar, no es posible cambiar el nombre de varios ejemplares de un grupo a la vez. Esto puede resultar muy útil si desea cambiar a la vez el nombre de decenas o cientos de ejemplares con el mismo nombre.

![](<../../.gitbook/assets/11 (6) (1).png>)

_**Nota:**_ _Si el cursor del ratón sale de la paleta, ya no podrá editar el cuadro de texto seleccionado. Esto es así en todas las paletas, por lo que asegúrese de mantener el cursor dentro del contorno de la paleta mientras edita cualquier elemento dentro de ella._

3 - Ahora, si selecciona una puerta de cristal de Groove Coffee u otra diferente y observa sus propiedades en la **paleta Propiedades** normal, verá que el nombre del **grupo** se ha actualizado para cada ejemplar, pero solo se ha cambiado el valor por defecto de la propiedad de **nombre** de ejemplar para las puertas de esta cafetería.

![](<../../.gitbook/assets/12 (3) (1).png>)

4 - Por último, veamos a continuación cómo este módulo de extensión ordena los distintos tipos de elementos:

1. Dibuje rápidamente una **Línea (L)**, un **Rectángulo (R)** y un **Cubo (Alt + B)** en cualquier lugar del modelo. Estos serán temporales, por lo que la ubicación precisa no es importante.
2. Vuelva a abrir la **paleta Properties Plus** si estaba cerrada y, a continuación, pulse **Ctrl + A** para seleccionar todos los elementos visibles en el modelo.
3. Examine el área **Selection Count** y observe que los elementos seleccionados se dividen en **bordes** (líneas), **caras**, **cuerpos**, (formas 3D compuestas de caras y bordes, como el cubo)**,** **grupos**, etc.

![](<../../.gitbook/assets/13 (3) (1).png>)

_**Nota:**_ _Este módulo de extensión también detecta_ _**vértices**, que se pueden crear con otro módulo de extensión denominado_ _**Generate Vertex**. Si desea experimentar, instale el_ _**módulo de extensión Generate Vertex**_ _y repita los pasos anteriores._
