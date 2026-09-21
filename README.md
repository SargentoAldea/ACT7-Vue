# ACT7-Vue
Actividad 7 en Vue, correcion de errores

1. Problema detectado: Arch en blanco
Archivo: Proveedores.vue
Posible causa: Simplemente se debe a que el archivo esta completamente en blanco, y vue nos dice que necesita de al menos un template para poder iniciar, debe de tener una estructura HTML para poder montar y representar aquel elemento a la hora de iniciar.

2. Problema detectado: Inconsistencia de nombres
Archivo:ItemsRecepcion.vue
Posible causa: Mas que nada parece ser problema de nombres o  tipo de dato.

3. Problema detectado: ¿Agregar no funca?
Archivo:ItemsRecepcion.vue
Posible causa: Parece ser que Agregar no crea o inserta como debería.

4. Problema detectado: Generación de ID
Archivo:ItemsRecepcion.vue
Posible causa: Similar al problema 2, en useRecepcionStore.js parece haber un "_seq", pero dentro de ItemsRecepcion.vue se hace uso de "Date.Now".

5. Problema detectado: Errores de Typeo
Archivo:App.vue
Posible causa: En general, como su nombre indica, simplemente son errores de typeo.

Actividad 7 - Correccion estado compartido

En este apartado se encontraron detalles que siendo honestos ya se encontraban marcados y que eran sencillos de reparar, como el cantidad '450', o el state comentado.
En lo que a mi respecta, creo que el estado compartido entre componentes es importante a la hora de que los componentes trabajen sobre los mismos datos en lugar de que cada cual tenga una copia propia.

Actividad 7 - Correccion gestion de libros

Los detalles en esta parte son más que nada el uso de "&&" o "||" para el largo del isbn, el "id: Date.now" el cual fue cambiado a "state._seq.libros++"" de manera que queda consistente con el store, del mismo modo se cambia el "anio_publicacion" por simplemente "anio", y aunque si bien era posible ver "l.anio" y "l.anio_publicacion" gracias a "l.anio ?? l.anio_publicacion" simplemente se dejo en "l.anio"

Actividad 7 - Correccion gestion de recepciones

En primer lugar se agrega un "return" en el if correspondiente a la hora de seleccionar proveedor, de modo que no siga de "Largo", al igual que el caso anterior se cambia el "Date.now" por "state._seq.recepciones++, finalmente se añade .number a un v-model de modo que queda "v-model.number="form.id_proveedor" para mantener número en todo momento

Actividad 7 - Correccion detalle recepcion

De forma sencilla, aqui se presentan detalles como por ejemplo que la función agregar al inicio no funcionaba debido a que no creaba nuevos objetos, creo que ese sería uno de los errores principales o ciertos errores de typeo, pero el principal se arreglo colocando el "nuevoItem", adempas de colocar validaciones basicas.
Si bien el id usaba un "Date.Now()" este fue reemplazado por un "state._seq.items++," para mejor consistencia y aprovechar lo creado anteriormente.

Actividad 7 - Totales y calculos de recepcion

En este caso lo que se hace en primera instancia en totalLibros es sumar en base a los items de cada recepción, es decir, se filtra, con ello se obtiene un total, por ejemplo, si el item 1 tiene 100 y el 2 200 el total debería de ser 300 siempre y cuando estos esten en la misma recepción, de manera similar el porcentajeProblemas trata con los items con el fin de registrar el total y luego los items que puedan ser problematicos, con ello es posible dividir y luego multiplicar por 100 para tener un porcentaje de items problematicos, a modo de ejemplo, si tenemos 10 items de una recepción de los cuales 5 estan marcados como mixto o dañado, el procentaje a marcar debería de ser 50% independientemente de la cantidad de libros que estos contengan dado que nos estamos refiriendo a los items como tal.