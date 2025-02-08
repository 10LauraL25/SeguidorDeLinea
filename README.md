CÁMARA
Este código en Python permite la gestión de un sensor de cámara OV7670 y una pantalla OLED mediante diferentes bibliotecas y módulos. Se importan librerías esenciales como sys, time, pwmio, digitalio, busio y board.

Se configuran salidas PWM con una frecuencia de 2000Hz y se establecen los pines de datos y control para la cámara. Aunque la biblioteca adafruit_ssd1306 para la pantalla OLED está comentada, se importa el módulo adafruit_ov7670 para gestionar la cámara OV7670.

El código inicia la comunicación I2C con la cámara y define ajustes como el tamaño de imagen, el espacio de color y la orientación vertical. Además, se imprime el tamaño de la imagen capturada y se configura un buffer de píxeles para almacenar la imagen procesada.

Este código está diseñado para funcionar con CircuitPython en un microcontrolador compatible, permitiendo la captura y procesamiento de imágenes, así como su visualización en una pantalla OLED.

OLED
Este código implementa un tacómetro virtual en una pantalla OLED, utilizando un sensor de RPM.

Se importan las bibliotecas necesarias, como machine para el control de hardware, ssd1306 para gestionar la pantalla OLED, time para manejar el tiempo y random para generar valores aleatorios de RPM.

Se configuran la pantalla y las dimensiones de los elementos gráficos, como las barras de nivel y la flecha que indica la dirección del tacómetro. La función get_random_rpm() genera valores aleatorios de RPM dentro de un rango determinado, mientras que get_arrow_direction(rpm) asigna la dirección de la flecha según el valor de RPM.

El dibujo del tacómetro en la OLED se realiza a través de la función draw_tachometer(rpm), que representa gráficamente los niveles de RPM y la dirección de la flecha. Finalmente, un bucle infinito actualiza la pantalla cada segundo con un nuevo valor de RPM, simulando el comportamiento de un tacómetro real.

PERCEPTRÓN
Este código implementa un perceptrón, una red neuronal simple que toma decisiones basadas en datos de entrada.

Se define la clase Perceptron, que incluye métodos para inicializar pesos y sesgos, realizar predicciones y entrenar el modelo mediante ajuste de pesos en función del error y la tasa de aprendizaje.

Durante el entrenamiento, el perceptrón analiza un conjunto de datos de entrada y etiquetas, modificando sus parámetros para mejorar la precisión de sus predicciones.

El código también captura imágenes y procesa píxeles de diferentes regiones para calcular promedios de intensidad, permitiendo detectar características específicas en la imagen. En función de estos valores, se ajusta el movimiento de los motores del robot, lo que le permite seguir una línea o corregir su dirección.

Además, se incluye una función que detecta si un botón ha sido presionado; en caso afirmativo, el perceptrón se vuelve a entrenar con datos actualizados.

En resumen, este código combina inteligencia artificial con control robótico, utilizando un perceptrón para procesar datos visuales y optimizar el desplazamiento del robot.

Q-LEARNING
Este código implementa el algoritmo de aprendizaje por refuerzo Q-Learning, en el que un agente toma decisiones basadas en un conjunto de estados y acciones.

Se desarrolla la clase QLearningAgent, que define los parámetros clave del agente, como el número de estados y acciones, la tasa de aprendizaje y el factor de descuento.

choose_action(): Implementa la estrategia epsilon-greedy, permitiendo al agente explorar nuevas acciones o explotar las que ya ha aprendido.
update(): Modifica la tabla Q con base en las recompensas obtenidas y los errores de predicción.
get_state(): Convierte los valores de los píxeles de la imagen en un estado numérico binario, facilitando el procesamiento de datos.
En el bucle principal, el código captura imágenes, analiza la intensidad de luz reflejada en los píxeles y ajusta los motores del robot según la detección de la línea. Dependiendo de la posición de la línea en la imagen, el agente decide girar, corregir su trayectoria o avanzar en línea recta.

A medida que el sistema recopila datos, el agente Q-Learning ajusta sus valores en la tabla Q, mejorando su capacidad para tomar decisiones óptimas en futuras iteraciones.

Este enfoque de aprendizaje por refuerzo permite al robot optimizar su desempeño, asegurando un seguimiento eficiente de la línea con el tiempo.
