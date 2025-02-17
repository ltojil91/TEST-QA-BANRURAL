# Test Strategy - Adivina tu número

## Descripción del Proyecto
El juego "Adivina tu número" es un juego en el que el jugador debe adivinar un número aleatorio generado por la computadora.

## Errores Encontrados y Soluciones

### . Error 1: No pasa ningún envento 
- **Descripción del error**: Al realizar una prueba sin ingresar un número y precionar el boton "Ingresar el número aleatorio" no genera ninguna acción.
- **Solución**: Se reviso la consola y verificamos la parte donde nos mostraba el error y era este comando `guessSubmit.addeventListener('click', checkGuess` se procedio a corregirlo de la siguiente manera: `guessSubmit.addEventListener('click', checkGuess`

### . Error 2: No pasa ningún envento 
- **Descripción del error**: Se volvio a realizar la prueba sin ingresar un número y nos desplega un mensaje "Incorrecto" con color de fondo "VERDE".

- **Solución**: Se corrio el codigo en la parte de la function checkGuess, ya que la parte del manejo de intentos y mensajes estaban invertidas, también se corregio la parte de `if(userGuess === randonNumber) ` ya que que es un string y randonNumber es un entero por lo cual el userGuess se hizo la conversión a entero `parseInt(userGuess)`. Y se cambio el color naranja por negro así como lo dicen las especificaciones.

### . Error 3: No acumula el conteo
- **Descripción del error**: Al momento de ingresar números no genera el conteo ni muestra el mensaje, se reviso consola y el error nos lo indica en `  const lowOrHi = document.querySelector('.lowOrHi');` 

- **Solución**: Se agrego el puntp que faltaba a la declaración de la variable. Quedando de la siguiente manera `const lowOrHi = document.querySelector('.lowOrHi');`

### . Error 4: Solo permite 5 intentos:  
- **Descripción del error**: Solamente permite 5 intentos y no 10 como lo indican las especificaciones
- **Solución**: Se modifico el codigo: `const ATTEMPS = 5` por `const ATTEMPS = 10`

### . Error 5: El boton resetGame no funciona:
 - **Descripción del error**: Al momento de querer empezar otro juego, se presiona el boton "comienza un nuevo juego" pero al dar click no genera ningún evento.
 - **Solución**: Se modifico el codigo: `addeventListener` por `addEventListener`

### . Error 6: Numeros aleatorios:
 - **Descripción del error**: Solamente estaba generando números aleatorios de hasta 10 y las especificaciones dicen que debe ser de 1 a 10.
 - **Solución**: Se modifico el codigo: `Math.random()*10` por `Math.random()*100`

### . Error: Número aleatorio siempre es 1

- **Descripción del error**:  el número aleatorio siempre era 1 debido a la forma en que se generaba en la función  restGame().
- **Solución**: Se modifico el codigo `randomNumber = Math.floor(Math.random()) + 1;` a `randomNumber = Math.floor(Math.random() * 100) + 1;` ya con esto genera números aleatorios de 1 a 100.


# Recomendaciones
- **Pruebas adicionales**: Se recomienda probar el juego en diferentes navegadores para asegurarse de que se comporta de la misma manera en todos ellos.
- **Mejora de la experiencia de usuario**: Sería útil agregar un mensaje de error si el jugador ingresa un valor no válido, como texto en lugar de un número. Ya lo hace pero sería ideal que muestre un mensaje diciendo "Usted ingreso un texto, debe de ingresar un número de 1 a 100"

## Herramientas Utilizadas
- Navegador web (Chrome, Edge)
- Consola de desarrollo para detectar errores
-Git Bash
-Visual Studio code