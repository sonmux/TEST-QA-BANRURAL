# Objetivo  
Realizar pruebas funcionales y correcciones al juego "Adivina tu número" para garantizar su correcto funcionamiento

## Errores encontrados y soluciones
1. Número aleatorio incorrecto
> [!CAUTION]
> Error: Se estaba generando un número aleatorio con Math.random() * 10, lo que no garantizaba un número entero entre 1 y 100.
> [!TIP]
> Solución: Se corrigió a Math.floor(Math.random() * 100) + 1 para generar números enteros en el rango correcto.

2. Incorrecta selección del elemento lowOrHi
> [!CAUTION]
> Error: La referencia const lowOrHi = document.querySelector('lowOrHi') estaba mal escrita, faltaban los . para seleccionar correctamente la clase.
> [!TIP]
> Solución: Se corrigió a const lowOrHi = document.querySelector('.lowOrHi');

3. Errores en addEventListener
> [!CAUTION]
> Error: Se usó addeventListener en lugar de addEventListener en los eventos de los botones.
> [!TIP]
> Solución: Se corrigió a addEventListener.

4. Validación incorrecta de entradas
> [!CAUTION]
> Error: No se validaba si el usuario ingresaba un número entero dentro del rango 1-100.
> [!TIP]
> Solución: Se agregó una validación con isNaN(userGuess), Number.isInteger(userGuess), y restricciones de rango. Se muestra una alerta si la entrada es inválida y no se cuenta como intento.

5. Mensajes incorrectos al usuario
> [!CAUTION]
> Error: Los mensajes de "Incorrecto! El número es mayor!" y "Incorrecto! El número es menor!" no se mostraban en color negro.
> [!TIP]
> Solución: Se ajustó lastResult.style.backgroundColor = 'black'; antes de actualizar lowOrHi.textContent.

6. Error en la comparación de intentos
> [!CAUTION]
> Error: La lógica de conteo de intentos estaba invertida. Mostraba "Pérdistes" cuando se adivinaba y "Felicitaciones" cuando se fallaba.
> [!TIP]
> Solución: Se corrigió el flujo lógico para que muestre "Felicitaciones" si el usuario acierta y "Pérdistes" si se queda sin intentos.

## Plan de Pruebas

> [!IMPORTANT]
> Prueba de generación del número aleatorio
> Verificar que el número generado está entre 1 y 100.

> [!IMPORTANT]
> Prueba de validación de entrada
> Ingresar valores no numéricos y verificar que no se incrementen intentos.
> Ingresar valores fuera del rango permitido y validar la alerta.

> [!IMPORTANT]
> Prueba de comparación de números
> Ingresar valores mayores y menores al número objetivo y validar los mensajes correctos.

> [!IMPORTANT]
> Prueba de intentos máximos
> Verificar que el juego finaliza correctamente tras 10 intentos fallidos.

> [!IMPORTANT]
> Prueba de reinicio del juego
> Validar que tras reiniciar se genera un nuevo número y los intentos se reinician.
