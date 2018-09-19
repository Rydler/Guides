# MODULOS

##### os  - Modulo que proporciona una forma portatil de utilizar la funcionalidad dependiente del sistema operativo

####  METODOS

<code>os.chdir(path)</code> : Cambia el directorio de trabajo actual al path especificado.

<code>os.getcwd</code> : Devuelve una cadena que representa el directorio del trabajo actual

<code>os.listdir(path)</code> : Devuelve una lista que contiene los nombres de las entradas en el directorio indicado por esa path. La lista esta en orden arbitrario.

<code>os.rename(src, dst)</code> : Cambia el nombre del archivo o directorio **src** a **dst**.

* * *

##### time - Modulo que proporciona funcionalidades realcionadas con el tiempo

#### METODOS

<code>time.sleep(secs)</code> : Suspende la ejecucion del hilo actual durante el numero de segundos especificados. el argunmento puede ser un nuemero de coma flotante para indicar un tiempo de suspension mas preciso.

<code>time.ctime()</code> : 

* * *

##### turtle - Modulo que permite dibujar e introducir la programacion en los niños. Era parte del lenguaje de programación Logo original, desarrollado por Wally Feurzig y Seymour Papert en 1966.

#### METODOS

<code>turtle.bgcolor(*args)</code> : Permite cambiar el color de fondo de la pantalla. 

<code>turtle.circle(radius, extent=None, steps=None)</code> : Dibuja un círculo con un radio dado. El centro es unidades de radio que quedan de la tortuga; la extensión, un ángulo, determina qué parte del círculo se dibuja. Si la extensión no está dada, dibuja todo el círculo. Si la extensión no es un círculo completo, un punto final del arco es la posición actual del lápiz. Dibuje el arco en sentido contrario a las agujas del reloj si el radio es positivo, de lo contrario en el sentido de las agujas del reloj. Finalmente, la dirección de la tortuga cambia por la cantidad de extensión.

<code>turtle.exitonclick()</code> : Permite salir al hacer click sobre la pantalla

<code>turtle.forward(distance)</code> : Mueva la tortuga hacia delante en la distancia especificada, en la dirección en que se dirige la tortuga.

<code>turtle.left(angle)</code> : Gira a la tortuga a la izquierda en unidades angulares. 

<code>turtle.right(angle)</code> : Gira a la tortuga a la derecha en unidades angulares.

<code>turtle.speed(speed=None)</code> : Limita la velocidad con la cual se mueve la tortuga.

* * *

##### webbrowser - Permite inicializar el browser pasando como parametro cualquier URL

#### METODOS

<code>webbrowser.open(url, new=0, autoraise=True)</code> : Muestra la URL usando el navegador predeterminado. Si **new** es 0, la url se abre en la misma ventana del navegador si es posible. Si **new** es 1, se abre una nueva ventana del navegar si es posible. Si **new** es 2 se abre una pestaña del navegador. Si **autoraise** es True, la ventana del navegador se levanta de ser posible.

***

# LOOPS

##### while condition:
##### for value in variable:
