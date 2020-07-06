# Introducción 
[Link a sesión](https://owncloud.gwdg.de/index.php/s/xoC1OUE5IFy7g8U)

Esta es la primera sesión del curso "Machine Learning for Physicist" 2020. Previo a esta sesión se recomienda leer “Computing Machinery and Intelligence” de Alan Turing (1950) y “Perceptron” donde Rosenblatt habla de este concepto (1957), ambos documentos se encuentran en esta carpeta.

Ideas: 

1. Actualmente redes neuronales profundas pueden hacer muchas cosas, por ejemplo, pueden reconocer imágenes y los elementos en estas; sin embargo, dado a que son aproximaciones (de alguna manera) probabilísticas, siempre se puede estar mal.

2. Computadoras con IA ya han vencido a los mejores jugadores humanos en ajedrez, y mas recientemente, en Go.

3. Algo más sencillo que las redes neuronales pueden hacer, es aproximar cualquier función (en general, en $R^n$), y lo interesante de este hecho es que dicha función puede ser altamente no lineal, y aun así ser bien aproximadas por la red.

4. En este curso, más que Machine Learning en general, ser verán Deep Neural Networks. El hecho de que sea para físicos se refiere a que las aplicaciones que se verán desde la mitad hasta el final del curso van orientadas a esta rama.

5. Para poder tomar el curso, es necesario únicamente un background en matemáticas (primer año de Lic. en física aprox) y es preferible experiencia en algún lenguaje de programación.

6. Algunas de las preguntas que responderemos en este curso:
    - ¿Cómo luce una red neuronal?
    - ¿Cómo las entrenamos de manera eficiente?
    - ¿Cómo se pueden reconocer imágenes?
    - ¿Cómo se puede aprender con un conjunto compacto de datos sin información adicional?
    - Aplicaciones modernas en la ciencia.
    
7. Usaremos Python (Obvio), y más adelante (a partir de la tercera sesión) comenzaremos a usar Keras y TensorFlow.

## Imitation Game

Es una prueba que una computadora debe ser capaz de pasar para poder decir que esta piensa (de alguna manera) propuesta por Alan Turing. En esta prueba, hay un interrogador y dos interrogados, A y B. Uno de los dos es un ser humano, y otro una computadora cuyo objetivo es *imitar* a un ser humano. No hay contacto físico o visual, únicamente respuestas escritas. Al final de la prueba, después de unos minutos de preguntas, el interrogador debe determinar cuál de los dos sujetos, A O B, es la máquina. En caso de que esta decisión sea aleatoria (dado que el interrogador no tiene indicios suficientes), se considera que la maquina pasó la prueba.

Turing decía que computadoras de aproximadamente $10^9$ de capacidad de almacenamiento (alrededor de 1Gb) podrían pasar esta prueba, pero sabemos que no lo hacen. Ya hay programas (bots) que realizan la prueba de manera impresionante.

Ideas: 

1. Entrenar una red neuronal es más parecido a un proceso experimental, por lo que muchas veces es casi imposible describir exactamente cómo funciona (ie que hace cada capa).

2. Turing también muestra una idea inicial de aprendizaje reforzado, hablando sobre premios y castigos en el aprendizaje de estas *maquinas*.

## Perceptrones

La idea de redes neuronales se basa en el uso de **perceptrones**, los cuales están inspirados por neuronas reales. Se pretende imitar el funcionamiento del cerebro biológico.

En general, un perceptrón consta de tres partes: primero, un sistema sensor (donde entra el input), un sistema de respuesta (output) y un sistema de asociación (que es lo que procesa el input para emitir el output).