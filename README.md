## Práctica 1. Primeros pasos con OpenCV

### Tarea 1: Tablero de ajedrez
Generación de un patrón de tablero de ajedrez en blanco y negro a partir de una matriz (800 x 800) de ceros.

Se han usado bucles anidados para poner a 255 los elementos correspondientes de la matriz de modo que quede un tablero de ajedrez 8x8.

La imagen se muestra con *Matplotlib*.


### Tarea 2: Mondrian
Creación de una imagen al estilo Mondrian con las funciones de dibujo de *OpenCV*.

Primero se ha declarado el color del fondo y después se han dibujado los rectángulos rellenos por encima.


### Tarea 3: Detección de píxel más claro y más oscuro a partir de la imagen de la cámara

Para detectar los píxeles correspondientes, se han seguido estos pasos:
 - Convertir la imagen a escala de grises para trabajar en una sola capa.
 - Aplicar la función *where* junto a *max* y *min* (todas funciones de *Numpy*) para hallar la posición de los píxeles de valor máximo (más claros) y mínimo (más oscuros) respectivamente. De detectarse varios píxeles con el mismo valor, se utiliza el primero encontrado.
 - Dibujar un círculo sobre los píxeles encontrados usando las funcinoes de dibujo de *OpenCV*.

| Píxel      | Color Asignado |
|------------|----------------|
| Más oscuro | Azul           |  
| Más claro  | Rojo           |

La imagen de la cámara se obtiene con la función *VideoCapture* de *OpenCV* y el resultado se muestra con *imshow* de la misma librería.

Para cerrar la ventana, pulsar la tecla **escape**.

### Tarea 4: Propuesta pop art

Se ha realizado un collage con los bordes detectados en la imagen.
Las esquinas superior izquierda e inferior derecha se dibujan en blanco sobre negro y las demás en negro sobre blanco.

Como en la tarea anterior, la imagen se obtiene con *VideoCapture*.

Primero, se reduce el tamaño de la imagen con *resize* (*OpenCV*).

Después, se obtienen los bordes con la función *canny* (*OpenCV*).
Esto produce una imagen negra con los bordes en blanco.

A continuación, se invierten los bits de la imagen de los bordes (*bitwise_not*, *OpenCV*) para obtener la imagen con el fondo blanco y los bordes en negro.

Por último se monta el collage en una matriz del tamaño de la imagen original.

El resultado se muestra con *imshow* de *OpenCV*.

Para cerrar la ventana, pulsar la tecla **escape**.

---