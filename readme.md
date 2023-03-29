# Electrónica IV. Trabajo práctico 2. Reimplementación de TP 1 en C

En este práctico deberás implementar los mismos algoritmos que el TP 1 (repetidos por conveniencia) en lenguaje C. Alternativamente puedes usar *otros algortimos para la misma tarea* (los algoritmos dados no son especialmente eficientes).

Antes de comenzar asegúrate de lo siguiente:

- Han realizado el [TP1][eiv23-tp1]
- Todos los miembros de tu equipo tienen cuenta en GitHub
- El encargado de mantener los repositorios del equipo ha clonado [el repositorio de este práctico][eiv23-tp2]
- Todos los miembros del equipo tienen acceso de escritura al repositorio del equipo para este práctico.
- Todos los miembros del equipo que cuentan con PC han instalado las herramientas (ver [TP1][eiv23-tp1] por detalles)

## Implementación de algoritmos

Para completar este práctico deberás implementar los algoritmos del TP1 u otros equivalentes en lenguaje C. Al igual que en el práctico anterior, tu código será una parte de un programa mayor que lo ejecutará y comprobará sus resultados. El archivo `lib\practico\practico.c` contiene una plantilla que deberás completar con tu solución.

### Suma (suma)

Dados dos números enteros de 32 bits calcular y devolver su suma.

![a,b -> a+b][fig_suma]

### Sumatoria (sumatoria)

Dado un arreglo de enteros de 32 bits de longitud **n** y dirección base **b**. Calcular la sumatoria del arreglo, **usando un acumulador de 64 bits**, y devolver el resultado de 64 bits. *El arreglo dado no puede ser modificado por el programa.*

![n,b -> A = b[0]+...+b[n]][fig_sumatoria]

### Posicion máximo (posicion_maximo)

Dado un arreglo de enteros de 32 bits de longitud **n** y dirección base **b**. Devolver la posición (índice) del máximo número en el arreglo. *El arreglo dado no puede ser modificado por el programa.*

![n,b -> k : b[i] <= b[k] para todo i en {0,..,n-1}][fig_posmax]

Notas:

- Si hay más de un máximo, retornar la posición del primero.
- El primer número tiene posición 0, el segundo posición 1, etc.

### Ordenar de menor a mayor en el lugar (ordenar_en_sitio_menor_a_mayor)

Dado un arreglo de enteros de 32 bits de longitud **n** y dirección base **b**. Ordenar el arreglo de menor a mayor en su sitio (intercambiando posiciones de los números hasta que esté ordenado). *En este caso el programa **sí** deberá modificar el arreglo dado.*

![n,b -> void : luego de ejecutar subprograma, b[i] <= b[j] para todo i <= j con i,j en {0,...,n-1}][fig_ordenar]

## Uso de pruebas de software para verificar la solución

Este proyecto hace uso del emulador Renode, por lo tanto no necesitas tener el hardware para completarlo. El proyecto tiene un conjunto de pruebas para verificar el funcionamiento de las rutinas que debes escribir. Para ejecutar las pruebas, en Visual Studio Code, presiona Ctrl+Shift+P y escribe `platformio:test` luego enter. Puede demorar un tiempo en ejecutarse la simulación. Hay en total 16 casos de prueba, definidos en `test/test_algoritmos/test_main.c. Se prueban tres casos para la suma, seis casos para la sumatoria, dos casos para posición del máximo y dos casos para ordenación.  

Recuerda: Si no pasan las pruebas, tu solución no es válida. Si pasan puede ser válida o nó, habra que revisarla en detalle. Pero si la diseñaste cuidadosamente y pasa las pruebas lo más probable es que sea válida.

## Depuración

Puedes depurar el proyecto usando Renode, para ello posiciónate en la línea de tu código que te interesa y haz click a la izquierda del número de linea para establecer un breakpoint. Después presiona F5 para depurar. Aparecerá la terminal de Renode y otra ventana con la salida de la usart1 (por donde salen los resultados de las pruebas). Después de unos momentos iniciará el cliente del depurador, el que podrás ver en la ventana de VSCode. El depurador quedará detenido al inicio del programa. Presiona F5 para continuar hasta tu punto de interrupción y luego F11 para avanzar un paso o F10 para avanzar un paso saltando llamadas a procedimiento. Si deseas ver más de una prueba puedes continuar con F5 hasta el siguiente punto de interrupción.

Nota: La emulación es limitada, el debugger no tiene acceso a los periféricos emulados (pero sí a la memoria y los registros del procesador). Además la emulación de los periféricos no pretende ser perfecta.

## Referencia en línea lenguaje C

Una referencia en línea de lenguaje C es [la parte de lenguaje C del sitio cppreference, versión en español][cppreference_c_es]. El compilador GCC soporta al menos C99 con algunas extensiones. Nota: No todo el sitio está actualmente traducido. Si hay algo que no encuentras puedes consultar [la versión en inglés][cppreference_c].

[eiv23-tp1]: https://github.com/fmirandabonomi/eiv23-tp1
[eiv23-tp2]: https://github.com/fmirandabonomi/eiv23-tp2
[cppreference_c_es]: https://es.cppreference.com/w/c
[cppreference_c]: https://en.cppreference.com/w/c
[fig_suma]: suma.png
[fig_sumatoria]: sumatoria.png
[fig_posmax]: posicion_maximo.png
[fig_ordenar]: ordenar_en_sitio_menor_a_mayor.png
