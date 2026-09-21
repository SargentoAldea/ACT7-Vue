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