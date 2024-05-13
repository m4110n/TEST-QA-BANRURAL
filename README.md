# Prueba de tester 1
Esta prueba evalúa conocimientos de programación en base a una situación que puede pasar dentro de un proyecto de software.
## Software necesarios
* [GIT](https://git-scm.com/downloads)
* Cualquier navegador WEB
## Instrucciones antes de empezar
1.  Crear una cuenta en [Github](https://git-scm.com/book/es/v2/GitHub-Creaci%C3%B3n-y-configuraci%C3%B3n-de-la-cuenta).
2.  Crear un [fork](https://docs.github.com/es/get-started/quickstart/fork-a-repo) a este repositorio.
3.  Clonar el repositorio forkeado en tu computadora.
4.  Úbicate en el repositorio raíz del proyecto (Ubicación del proyecto forkeado en tu computadora).
5.  Abrir desde del navegador el archivo index.html de este proyecto.
## Casos de usos
Un banco financiero implementó el juego, Adivina tu número, la cual consiste en adivinar un número entre 1 al 100 durante 10 intentos. Así mismo para facilitar dicho juego se debe cumplir los siguientes requisitos:
* El número a adivinar debe pertenecer al conjunto de los enteros (e.g. 1, 2, 3...)
* El número que ingresará el jugador debe pertenecer al conjunto de los enteros (e.g. 1, 2, 3...), en caso que no ingrese un número entero, debe mostrarse una alerta al usuario y no se debe incrementar un intento de prueba.
* Sí el número que ingresó el jugador es mayor al número a adivinar, se debe mostrar el siguiente mensaje en color negro: "Incorrecto! El número es mayor!", en caso que sea menor, se debe mostrar: "Incorrecto! El número es menor!".
* Si después de 10 intentos, el usuario no adivina el número, se debe mostrarse el mensaje de color rojo: "!!!Pérdistes!!!"
* Si el usuario adivina el número antes de los 10 intentos, se debe mostrar el mensaje de color verde: "Felicitaciones! adivinaste el número!".
## Situación del proyecto.
El desarrollador implementó toda la interfaz gráfica, y así mismo la lógica del juego en el archivo index.html (Con HTML, Javascript y CSS), sin embargo el equipo de desarrollo cometió el error de no testear dicho proyecto, y lo colocaron en los servidores de producción. Para su sorpresa, al momento de que el cliente lo vió... ¡NO FUNCIONABA NADA!
Dado a esta experiencia, el banco financiero contrató a un tester para realizar las pruebas respectivas con la finalidad de que el proyecto funcione correctamente de acuerdo a los requerimientos dados.
## Plan de ataque
Como tester debes solucionar este problema en tu repositorio de github, así mismo debe presentarle al equipo de desarrollo todos los errores que fuiste encontrando y corregiendo (i.e. Una breve descripción del error y su solución respectiva). Dentro del archivo test-strategy.md, igualmente el lider del equipo recomendó a cada tester, ver la consola del navegador de web para identificar más rápido los errores del proyecto.
## Entregables
Como entregables debe presentar lo siguiente:
* El archivo index.html corregido de acuerdo a las observaciones de testeo, cabe mencionar que este archivo debe ser funcional (Al momento de abrir el proyecto, debe funcionar de acuerdo a la lógica de negocio planteado en este ejercicio).
* El plan de ataque test-strategy.md
## Recursos:
* Event Target: https://developer.mozilla.org/es/docs/Web/API/EventTarget

* ## ERRORES ENCONTRADOS
* Errores Encontrados:

1. Generación de Número Aleatorio:
   - El código original generaba un número aleatorio entre 0 y 9 utilizando `Math.random() * 10`. Sin embargo, el juego requería un número entre 1 y 100. Este error podría afectar la experiencia del juego ya que los usuarios esperan adivinar un número dentro de ese rango.
   
2. Error Tipográfico en Constante:
   - La constante `ATTEMPS` fue definida con una ortografía incorrecta como `ATTEMPS` en lugar de `ATTEMPTS`. Este error tipográfico podría provocar un mal funcionamiento del juego si la constante se utiliza en otros lugares del código.

3. Selección de Elemento HTML Incorrecto:
   - En la línea `const lowOrHi = document.querySelector('lowOrHi');`, se intentó seleccionar un elemento HTML con la clase `lowOrHi`, pero se omitió el punto antes del nombre de la clase. Esto provocaría que el código no seleccionara el elemento deseado y causaría un mal funcionamiento en la actualización de la pista de si el número es mayor o menor.

4. Error de Sintaxis en el Método `addEventListener`:
   - En dos lugares del código, se utilizó el método `addeventListener` en lugar de `addEventListener`. Este error de sintaxis causaría que los eventos no se vinculen correctamente a los elementos HTML y afectaría la funcionalidad del juego.

5. Generación Incorrecta de Número Aleatorio al Reiniciar el Juego:
   - Al reiniciar el juego, se intentó generar un nuevo número aleatorio utilizando `Math.floor(Math.random()) + 1`, lo cual es incorrecto. Esto generaría siempre el número 1, lo que no es lo esperado para un juego de adivinanzas. El código debería haber utilizado `Math.floor(Math.random() * 100) + 1` para generar un número aleatorio entre 1 y 100.

Cambios Realizados:

1. Generación de Número Aleatorio:
   - Se corrigió la generación del número aleatorio utilizando `Math.floor(Math.random() * 100) + 1`, asegurando que esté dentro del rango requerido para el juego.

2. Corrección de Ortografía en Constante:
   - Se corrigió la ortografía de la constante `ATTEMPTS` para que coincida con su uso en el código, evitando posibles errores tipográficos futuros.

3. Selección Correcta de Elemento HTML:
   - Se añadió el punto antes del nombre de la clase al seleccionar el elemento HTML con la clase `lowOrHi`, asegurando así la correcta selección del elemento y la actualización de su contenido.

4. Corrección de Sintaxis en el Método `addEventListener`:
   - Se corrigió la sintaxis del método `addEventListener` en dos lugares del código, asegurando que los eventos se vinculen correctamente a los elementos HTML y funcionen como se espera.

5. Generación Correcta de Número Aleatorio al Reiniciar el Juego:
   - Se corrigió la generación del número aleatorio al reiniciar el juego utilizando `Math.floor(Math.random() * 100) + 1`, garantizando que se genere un número aleatorio dentro del rango requerido para el juego.

Estos cambios aseguran que el juego funcione correctamente y proporcione una experiencia de usuario satisfactoria.
