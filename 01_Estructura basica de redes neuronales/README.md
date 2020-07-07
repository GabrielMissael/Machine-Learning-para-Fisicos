# Estructura básica de redes neuronales.

[Link a sesión](https://www.video.uni-erlangen.de/clip/id/10611)

## Overview

Esta es la segunda sesión del curso donde, a manera de resumen, vimos la estructura general que tiene una red neuronal, y después aplicamos y visualizamos la primera red neuronal profunda para aproximar funciones. En general, vimos como implementar el "forward-pass".

Para esta sesión, hay tres notebooks proporcionados por el instructor (que se encuentran en la carpeta de Tutorials). El primero trata la sesión en general, el segundo muestra como visualizar redes neuronales de capaz arbitrarias con 2 inputs y 1 output, su salida así como su estructura. Finalmente en el 3 se visualiza como realizar ajuste 1-dimensional de una red neuronal a una curva.

## Tareas

Para esta sesión, se tienen 5 tareas:

1. Implement a network that computes XOR (arbitrary number of hidden layers); meaning: the output should be +1 for y1 y2<0 and 0 otherwise!
2. Implement a network that approximately or exactly computes XOR, with just 1 hidden layer(!)
3. Visualize the results of intermediate layers in a multi-layer randomly initialized NN (meaning: take a fixed randomly initialized multi-layer network, and then throw away the layers above layer n; and directly connect layer n to the output layer; see how results change when you vary n; you can start from the notebook 1
4. What happens when you change the spread of the random weights? Smart weight initialization is an important point for NN training.
5. Explore cases of curve fitting where there are several (non-equivalent) local minima. Is sampling noise helpful (i.e. the noise that comes about because of the small number of x samples)?

Estas tareas están resueltas en el notebook de Tarea.

## Notas de sesión.

Las neuronas (en general, la mente humana) inspiraron las redes neuronales. En general, se buscaba crear algo que pudiera "pensar" o hacer cosas sin tener que indicarlo. Una red neuronal es, obviamente, una red de neuronas. En general, toma una entrada en su capa input, y posteriormente devuelve un conjunto de valores, en su capa de output.

Generalmente se utilizan las redes neuronales para realizar reconocimiento de imágenes; la idea es que dicha red pueda identificar un objeto, a pesar de que no se haya mostrado ese objeto en una determinada posición, color, transformación, etc.

Por ejemplo, se puede crear una RN (red neuronal) para reconocer focos, y entonces se reconocerán todos los focos en cualquier foto (en teoría). Hay una competencia llamada **ImageNet** donde se premia a la mejor RN capaz de reconocer diversos objetos, con 1.2 millones imágenes de entrenamiento de más de 1000 objetos. En 2012 una RN logró tener un error rate de 7%, siendo pues mejor para reconocer imágenes que una persona.

Otras **aplicaciones** de RN son: Describir imágenes, colorear imágenes, traducir lenguajes, contestar preguntas de un texto breve, jugar videojuegos (las RN son particularmente buenas en videojuegos). En particular, en física: predecir propiedades de los materiales, clasificar fases de materia, representar funciones de onda cuánticas. 

### Curso histórico

- 1956: Dartmouth workshop on AI.
- 50/60: Perceptrons.
- 1980: Backpropagation.
- 80/90: Recurrent networks, convolutional networks. 
- 2000: Deep networks become practical.
- 2012: Deep nets for image recognition beat the competition ImageNet
- 2015: A deep net reaches expert level in "Go".

### Libros recomendados:
1. [Neural Networks and Deep Learning](http://neuralnetworksanddeeplearning.com/)
2. [Deep Learning](https://www.deeplearningbook.org/)

### Redes neuronales.

Una red neuronal se puede entender como una función de varias variables que depende de muchos parámetros y además es altamente no lineal. La unidad básica de construcción de una RN son las neuronas y las conexiones entre ellas. Las conexiones se dan entre neuronas de capaz adyacentes. En general, está la capa input, las capas ocultas y la capa de output. 

El **Output** de una neurona es una función $f(z)$, donde la variable $z$ depende de la suma de las entradas $y_j$, que es el output de la neurona j-esima de la capa anterior, multiplicadas por un peso $w_j$ que es un escalar que indica la fuerza de la relación entre esas neuronas, y finalmente se le suma un bias $b$ que es como una base del valor de $z$:

$
z = \sum\limits_{j} w_jy_j + b
$

Una vez calculada $z$ se calcula $f(z)$, donde la función $f$ puede ser cualquier función (reLU (rectified linear unit), sigmoid, seno, logaritmo, línea, parábola, etc). Ese valor corresponde al output de la neurona. 

Este proceso se realiza para cada neurona, y se avanza por capa. Cada neurona tiene un bias $b$ y una función asignada $f$, y cada conexión tiene un peso $w$. Este proceso de avanzar a las capas superiores, desde el input hasta obtener un output es llamado "feedfodward", donde se calcula un output desde un input. 

Para tener una notación general para una capa, considerando que $j$ es la neurona de output, $k$ es la neurona de input:

$
z_j = \sum\limits_{k} w_{jk}y_k^{in} + b_j
$

En notación vectorial/matricial:

$
z = wy^{in} + b
$

Finalmente, aplicamos las funciones no lineales por cada neurona:

$
y_j^{out} = f(z_j)
$

Notemos que solo se tiene una función por capa.

**Nota:** Es conveniente realizar los cálculos con matrices o vectores, particularmente en un lenguaje interpretado como Python.
