# Practica2_AA2

## Introducción:

En esta practica de la asignatura de Aprendizaje Automatico II, tendremos que hacer dos ejercicios implementando la herramienta Pytorch, una libreria de Python.


## Objetivos:

### Primera parte: Crea un supresor de ruido de imágenes con el MNIST

En este ejercicio hay que añadir ruido a una imagen del MNIST, con una función proporcionada por el profesor. Nosotros tendremos que crear un modelo MNIST que nos permita suprimir el ruido implementado en estas imagenes.

### Segunda parte: Hacer Super Resolución

En esta parte, tendremos que reducir el tamaño de las imagenes antes de ser entrenadas, para que la resolución de estas sea mas borrosas, y luego modificar el CNN para que pueda mejorar la resolución de estas imagenes.


## Metodología:

### Primera parte:

En esta primera parte, tenemos una función para añadir ruido proporcionada en el enunciado. Creamos un modelo, que en este caso lo hemos llamado Supresor, que tiene dos partes. Un encoder, que tiene una capa lineal que reduce la dimensionalidad de la entrada, activada por una función ReLu. Un decoder, que esta reconstruye la dimensionalidad original, que usa una función de activación Sigmoid. Acto seguido entrenamos el modelo y lo evaluamos


En esta segunda parte, modificamos el Autoencoder proporcionado en la practica. En el encoder lo primero que modificamos es en las dos primeras capas de convulcion mantener el stride a 1 para que no reduzca la dimensiones de las imagenes, y en la tercera capa de convulcion ponemos el stride a 2 para reducir el tamaño a la mitad. En el decoder, lo que haremos es tener tres capas de convulcion, pero en este caso, la ultima capa tendra tambien un Stride = 2, para que la imagen de salida sea del tamaño de la imagen original, antes de reducir el tamaño. En el entrenamiento, lo que hacemos es, antes de introducir las imagenes al modelo, reducimos su tamaño con la funcion nn.functional.interpolate()

## Resultados:

Por ultimos, podemos observan que tanto los resultados de la primera parte como los de la segunda, son buenos, teniendo una baja función de perdida, lo que nos puede indicar que nuestros modelos son buenos



#### Participantes:
- Denys Kavkalo Gumeniuk
- Manuel Alejandro Torrealba Torrealba (Y3895148C)
