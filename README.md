# SOLEMNE

## PROCESO DE RÉPLICA  

Primero definí **líneas guía** (que posteriormente borré) para poder ubicar correctamente las figuras dentro del canvas. Dibujé una línea horizontal y una vertical central, y a partir de eso fui agregando otras referencias. Esto me fue de gran ayuda, ya que una de las principales dificultades era poder ubicar mentalmente los objetos en el espacio. Estas líneas me ayudaron a **ordenar la composición** y tener mayor control sobre las posiciones.  

---  

Luego pasé a trabajar los **semicírculos**, que fue una de las partes que más me complicó. Al principio no lograba que se formaran correctamente, ya que no podía obtener semicírculos perfectos. Tuve que entender mejor el uso de los ángulos y ajustar los valores hasta lograr un resultado correcto.  

- Una vez que logré uno en la parte superior, pude replicar los demás de forma horizontal.  
- Lo mismo ocurrió con los dos semicírculos de abajo: una vez entendido el uso de los ángulos, solo fue necesario modificar las coordenadas de **X**.  

---  

Después trabajé el **rectángulo vertical superior**. Al ser un elemento centrado, fue relativamente simple. Sin embargo, apareció otra dificultad importante: el **orden del código**. Tuve que aprender a organizar las figuras según su jerarquía visual, entendiendo qué elementos debían ir encima y cuáles debajo.  

---  

Luego desarrollé toda la **parte superior izquierda**, incluyendo la elipse del "ojo", las tres líneas verticales y las dos líneas horizontales. Esta parte fue más sencilla, ya que al tener el centro definido, las proporciones se resolvieron de manera más intuitiva.  

Sin embargo, la **elipse** me costó, ya que no lograba que tuviera la forma exacta: muchas veces me quedaba muy circular o demasiado aplanada, así que tuve que ir probando con varios parámetros hasta llegar al definitivo.  

A partir de esto, la parte derecha se construyó más fácil, reutilizando código y ajustando principalmente el eje **X** y las alturas.  

---  

El **triángulo** fue otro punto importante. En clases me había costado construirlo, pero en este ejercicio logré hacerlo definiendo primero la punta y luego los dos puntos de la base. Esto me permitió tener un mayor control sobre su forma y ubicación dentro de la composición.  

---  

Posteriormente agregué los **rectángulos verticales rojos**, los puntos y el círculo central. Finalmente, construí los bloques inferiores azules a ambos lados.  

Esta última parte también fue bastante **simétrica**, lo que facilitó el proceso al poder copiar estructuras y modificar principalmente el eje **X**.  

---  

Una de las principales dificultades durante todo el proceso fue el manejo de los **stroke** y los colores. Muchas veces, al cambiar el trazo o el color para una figura específica, estos cambios afectaban a todas las figuras siguientes.  

Esto me obligó a ser más ordenada en el código, reasignando constantemente los parámetros como:  

- `stroke()`  
- `fill()`  
- `strokeWeight()` 

---
Otra de las dificultades que tuve fue el hecho de describir el proceso mientras avanzaba. Muchas veces iba trabajando directamente en el código y se me olvidaba ir registrando lo que estaba haciendo, lo que después hacía más difícil reconstruir los pasos. Sin embargo, una vez que me empecé a acostumbrar, comencé a usar un mismo formato para todas las descripciones, lo que facilitó mucho el proceso, ya que podía copiar y pegar la estructura y solo modificar lo que cambiaba en cada parte.  

---

## RESULTADO
<img width="1000" height="1000" alt="descarga (3)" src="https://github.com/user-attachments/assets/2fa77463-b118-4afa-828d-74b8b36afdd3" />



---


## CÓDIGO 


function setup() {
  createCanvas(500, 500); // canvas base, se asigna un canvas de 500 x 500 px
  angleMode(DEGREES); // modo de angulo
 
}

function draw() {
  background(240); // fondo, se asigna fondo gris
  stroke(0); // trazo base, se asigna color negro
  strokeWeight(2); // grosor base, se asigna grosor de linea en 2
  noFill(); // relleno base, se asigna sin relleno

  strokeWeight(5); // linea central, se asigna grosor de linea en 5
  line(0, 250, 500, 250); // linea central, se asigna linea horizontal guia al centro

  strokeWeight(2); // rectangulo vertical negro, se asigna grosor de linea en 2
  fill(0, 0, 0); // rectangulo vertical negro, se asigna relleno negro
  rect(220, 0, 60, 250); // rectangulo vertical negro, se asignan coordenadas del rectangulo central superior

  strokeWeight(2); // parametros posteriores, se reasigna grosor de linea en 2
  noFill(); // parametros posteriores, se reasigna sin relleno

  line(0, 72, 220, 72); // lineas superiores izquierda, se asigna primera linea horizontal
  line(0, 140, 220, 140); // lineas superiores izquierda, se asigna segunda linea horizontal

  line(280, 34, 500, 34); // lineas superiores derecha, se asigna primera linea horizontal
  line(280, 102, 500, 102); // lineas superiores derecha, se asigna segunda linea horizontal

  stroke(250, 0, 0); // ojo izquierdo, se asigna color rojo al trazo
  line(110, 80, 110, 90); // ojo izquierdo, se asigna barra vertical central sobre el ojo
  line(130, 80, 130, 90); // ojo izquierdo, se asigna barra vertical derecha sobre el ojo
  line(90, 80, 90, 90); // ojo izquierdo, se asigna barra vertical izquierda sobre el ojo
  stroke(0, 0, 0); // ojo izquierdo, se reasigna trazo negro
  fill(250); // ojo izquierdo, se asigna relleno blanco
  ellipse(110, 107, 78, 38); // ojo izquierdo, se asignan coordenadas y tamaño de la elipse exterior

  fill(0, 0, 250); // ojo izquierdo, se asigna relleno azul
  ellipse(110, 107, 22, 22); // ojo izquierdo, se asignan coordenadas y tamaño de la pupila

  stroke(250, 0, 0); // ojo derecho, se asigna color rojo al trazo
  line(385, 40, 385, 50); // ojo derecho, se asigna barra vertical central sobre el ojo
  line(405, 40, 405, 50); // ojo derecho, se asigna barra vertical derecha sobre el ojo
  line(365, 40, 365, 50); // ojo derecho, se asigna barra vertical izquierda sobre el ojo
  stroke(0, 0, 0); // ojo derecho, se reasigna trazo negro
  fill(250); // ojo derecho, se asigna relleno blanco
  ellipse(383, 68, 78, 38); // ojo derecho, se asignan coordenadas y tamaño de la elipse exterior

  fill(90, 230, 230); // barra vertical bajo ojo derecho, se asigna relleno celeste
  rect(375, 87, 20, 160); // barra vertical bajo ojo derecho, se asignan coordenadas y tamaño del rectangulo

  fill(0, 0, 250); // ojo derecho, se asigna relleno azul
  ellipse(384, 68, 22, 22); // ojo derecho, se asignan coordenadas y tamaño de la pupila

  fill(250, 0, 0); // rectangulos verticales centrales, se asigna relleno rojo
  rect(170, 251, 45, 250); // rectangulos verticales centrales, se asignan coordenadas del rectangulo izquierdo
  rect(285, 251, 45, 250); // rectangulos verticales centrales, se asignan coordenadas del rectangulo derecho

  fill(0, 0, 250); // triangulo central, se asigna relleno azul
  triangle(187.5, 251, 312.5, 250, 250, 362); // triangulo central, se asignan coordenadas de sus tres vertices

  fill(0, 0, 0); // semicirculos superiores, se asigna relleno negro
  strokeWeight(2); // semicirculos superiores, se reasigna grosor de linea en 2
  arc(62.5, 250, 125, 125, 180, 360); // semicirculo superior izquierdo, se asignan coordenadas, tamaño y angulo

  fill(250, 0, 0); // semicirculos superiores, se asigna relleno rojo
  arc(187.5, 250, 125, 125, 180, 360); // semicirculo superior centro izquierdo, se asignan coordenadas, tamaño y angulo
  arc(312.5, 250, 125, 125, 180, 360); // semicirculo superior centro derecho, se asignan coordenadas, tamaño y angulo

  fill(0, 0, 0); // semicirculos superiores, se reasigna relleno negro
  arc(437.5, 250, 125, 125, 180, 360); // semicirculo superior derecho, se asignan coordenadas, tamaño y angulo

  fill(250, 250, 250); // parametros posteriores, se asigna relleno blanco

  noStroke(); // semicirculos inferiores, se asigna sin trazo
  fill(0, 0, 0); // semicirculos inferiores, se asigna relleno negro
  arc(125, 250, 125, 125, 0, 180); // semicirculo inferior izquierdo, se asignan coordenadas, tamaño y angulo 
  arc(375, 250, 125, 125, 0, 180); // semicirculo inferior derecho, se asignan coordenadas, tamaño y angulo
  stroke(0); // se define el contorno en negro
  strokeWeight(2); // se asigna un grosor de 2 pixeles al contorno
  strokeCap(SQUARE); // se define que los extremos de las lineas sean rectos 
  fill(250, 0, 0); // se asigna un relleno rojo 
  arc(250, 250, 125, 125, 0, 180); // se dibuja un semicirculo centrado

  stroke(0); // circulo y puntos mas abajo, se reasigna trazo negro
  strokeWeight(6); // circulo y puntos mas abajo, se asigna grosor de punto en 10
  point(250, 412); // circulo y puntos mas abajo, se asigna punto superior
  point(250, 462); // circulo y puntos mas abajo, se asigna punto inferior
  strokeWeight(2); // circulo y puntos mas abajo, se reasigna grosor de linea en 2
  fill(250, 0, 0); // circulo y puntos mas abajo, se asigna relleno rojo
  ellipse(250, 437, 22, 22); // circulo y puntos mas abajo, se asignan coordenadas y tamaño del circulo central

  fill(0, 0, 250); // bloque izquierdo, se asigna relleno azul
  rect(37, 345, 95, 45); // bloque izquierdo, se asignan coordenadas y tamaño del rectangulo
  fill(0); // bloque izquierdo, se asigna relleno negro
  square(57, 390, 55); // bloque izquierdo, se asignan coordenadas y tamaño del cuadrado

  fill(0, 0, 250); // bloque derecho, se asigna relleno azul
  rect(368, 345, 95, 45); // bloque derecho, se asignan coordenadas y tamaño del rectangulo
  fill(0); // bloque derecho, se asigna relleno negro
  square(388, 390, 55); // bloque derecho, se asignan coordenadas y tamaño del cuadrado
}


---


## LINK

LINKS :[Github](https://editor.p5js.org/marianne88/sketches/I1pgzBkM-)


---

## DIBUJO

IMÁGEN: ![IMG_20260409_203858](https://github.com/user-attachments/assets/71f9ffe4-6cb2-4853-a557-6feaf0249e13)

---

## PROCESO DIBUJO

![IMG_20260326_205324 (1)](https://github.com/user-attachments/assets/fd7ffe2d-0017-4f5f-97c5-d0ecf8a1655c)



