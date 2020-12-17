# Guía de marcado para "Estructurar datos planetarios"
La siguiente guía describe una guía de calificación para el tema HTML del Área de aprendizaje de MDN - [Estructuración de datos planetarios] (https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Structuring_planet_data). Cada subtarea detallada en la evaluación se enumera a continuación, junto con una explicación de cuántas marcas vale la tarea.

Nota: Estas son pautas, no reglas escritas en piedra; por supuesto, usted es libre de usar su criterio sobre la concesión de calificaciones cuando se encuentra con un caso límite o algo que no está claramente definido.

La calificación general otorgada es de 34. Calcule su calificación final y luego divida por 34 y multiplique por 100 para obtener una marca de porcentaje. Como referencia, puede encontrar una [página marcada terminada] (planets-data.html) que recibiría las mejores calificaciones.

## Semántica de bloques / estructural

<dl>
  <dt> Dar a la tabla una estructura básica de alto nivel: un contenedor exterior, un encabezado de tabla y un cuerpo de tabla (3 puntos) </dt>
  <dd> Esto es bastante simple. El alumno solo necesita incluir un elemento <code> & lt; table & gt; </code> en la página, con un <code> & lt; thead & gt; </code> y <code> & lt; tbody & gt; </code> como hijos . </dd>
  <dt> Agregue el título proporcionado a su tabla. (2 puntos) </dt>
  <dd> Nuevamente, simple, pero debe colocarse en el lugar correcto: el título proporcionado debe colocarse en un elemento <code> & lt; caption & gt; </code>, justo debajo de la <code> & lt; table & gt de apertura. ; </code> etiqueta. </dd>
  <dt> Agregue una fila al encabezado de la tabla que contenga todos los encabezados de columna (5 puntos). </dt>
  <dd> El estudiante debe:
    <ul>
      <li> Coloque las celdas de la fila dentro de un elemento <code> & lt; tr & gt; </code> y use elementos <code> & lt; th & gt; </code> para las celdas porque son encabezados (2 marcas). < / li>
      <li> Coloque el texto del encabezado de la columna en cada celda correctamente, copiado de los datos sin procesar (1 marca). </li>
      <li> Deje un espacio de dos columnas al comienzo de la fila; es mejor hacerlo con una sola celda con <code> colspan = "2" </code> configurado, pero aceptaríamos dos celdas (2 puntos ). </dd>
      <li> Nota: Se recomienda asignar a la columna de nombres de planetas un encabezado de "Nombre", pero no perderán una marca si lo olvidan. </li>
    </ul>
  </dd>
  <dt> Cree todas las filas de contenido dentro del cuerpo de la tabla, recordando convertir todos los encabezados de fila en encabezados semánticamente (15 puntos). </dt>
  <dd> Esta es la parte más difícil de la tabla: requiere colocar todos los encabezados de las filas del grupo en las filas correctas y hacer que abarquen el número correcto de filas y columnas.
    <ul>
      <li> En primer lugar, cada fila debe colocarse dentro del <code> & lt; tbody & gt; </code> (1 marca). </li>
      <li> Cada fila debe contener un elemento <code> & lt; th & gt; </code> que contenga el nombre del planeta al principio seguido de nueve elementos <code> & lt; td & gt; </code> que contengan los datos del planeta (5 puntos ). Otorgue la máxima puntuación si esto es en su mayoría correcto con un par de errores tipográficos, pero comience a reducir la marca a su discreción si los puntos de datos importantes están equivocados, mal ubicados u omitidos. Quite dos puntos si los nombres de los planetas no están en los encabezados. </li>
      <li> La primera fila del cuerpo debe contener un elemento <code> & lt; th & gt; </code> adicional al comienzo, que contenga "planetas terrestres", con <code> rowspan = "4" </code> y <code> colspan = "2" </code> (2 puntos). </li>
      <li> La quinta fila del cuerpo debe contener dos elementos <code> & lt; th & gt; </code> adicionales al principio, que contengan "planetas jovianos" y "gigantes gaseosos" respectivamente. El primero necesita <code> rowspan = "4" </code>, y el segundo necesita <code> rowspan = "2" </code> (3 puntos). </li>
      <li> La séptima fila del cuerpo debe contener un elemento <code> & lt; th & gt; </code> adicional al principio, que contenga "gigantes de hielo", con <code> rowspan = "2" </code> (2 puntos ). </li>
      <li> La novena fila del cuerpo debe contener un elemento <code> & lt; th & gt; </code> adicional al principio, que contenga "planetas enanos", con <code> colspan = "2" </code> (2 puntos ). </li>
    </ul>
  </dd>
  <dt> Agregue atributos para que los encabezados de fila y columna se asocien de manera inequívoca con las filas, columnas o grupos de filas para los que actúan como encabezados (5 puntos). </dt>
  <dd>
    El alumno debe agregar el valor <code> scope </code> a todos los elementos <code> & lt; th & gt; </code>, dándoles los valores adecuados como se muestra a continuación:
    <ul>
      <li> <code> col </code>: todos los elementos <code> & lt; th & gt; </code> en la fila del encabezado de la tabla. </li>
      <li> <code> fila </code>: todos los elementos <code> & lt; th & gt; </code> que contienen nombres de planetas, y el que contiene "planetas enanos" (también es un encabezado sobre una sola fila). </li>
      <li> <code> rowgroup </code>: los elementos <code> & lt; th & gt; </code> que contienen "planetas terrestres", "planetas jovianos", "gigantes gaseosos" y "gigantes de hielo". </ li >
    </ul>
  </dd>
  <dt> Agregue un borde negro alrededor de la columna que contiene todos los encabezados de fila de nombres de planetas (4 marcas). </dt>
  <dd> La forma más sencilla de hacer esto es:
    <ol>
       <li> Agregue un elemento <code> & lt; colgroup & gt; </code> justo debajo del elemento <code> & lt; caption & gt; </code>. </li>
       <li> Dentro de este, anide dos elementos <code> & lt; col & gt; </code>, uno con un atributo <code> span = "2" </code> y el otro con un <code> style </ code > atributo a lo largo de las líneas de <code> style = "border: 2px solid black" </code>. </li>
       <li> Notas: Sería aceptable definir todas las columnas de la tabla dentro del colgroup, aunque no es necesario. Agregar el estilo a cada celda en la columna individual no sería aceptable; esto colocaría el estilo alrededor de cada celda de la columna, no de la columna. </li>
     </ol>
   </dd>
</dl>
