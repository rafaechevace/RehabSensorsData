# Informe del ejercicio de rehabilitación en realidad mixta — Terapeuta 2

## 1. Alcance del análisis

Se ha analizado el archivo `SESSION_20260518_124105_R3_RH.zip`, que contiene tres carpetas de sesión:

- `SESSION_20260518_124031_R2_RH`
- `SESSION_20260518_124105_R3_RH`
- `SESSION_20260518_124135_R4_RH`

Los datos disponibles corresponden a las rondas **2, 3 y 4**. La ronda 1 no está incluida en este ZIP, aunque los contadores acumulados indican que antes de la ronda 2 ya existían **10 aciertos**, **5 fallos** y **1700 puntos**. Por tanto, este informe se centra en las tres rondas realmente disponibles, que constituyen una ejecución válida y comparable entre sí.

El ejercicio se realiza con la **mano derecha** (`RH`) y cada ronda contiene 10 objetivos.

---

## 2. Resumen global de las rondas disponibles

| Métrica global | Resultado |
|---|---:|
| Rondas analizadas | 3 |
| Rondas completadas | 3 |
| Objetivos completados en las rondas analizadas | 30 |
| Aciertos | 30 |
| Errores de color | 2 |
| Timeouts | 0 |
| Intentos totales | 32 |
| Precisión global | 100,0 % |
| Tiempo efectivo total de rondas | 102,65 s |
| Ritmo medio global | 17,54 aciertos/min |
| Puntuación inicial en los datos disponibles | 1700 |
| Puntuación final acumulada | 12350 |
| Puntos obtenidos en las rondas disponibles | 10650 |
| Mejor combo acumulado | 13 |

El rendimiento funcional es alto: las tres rondas se completan, no se producen timeouts y la precisión global en las rondas disponibles es del **100,0 %**.

---

## 3. Resultados por ronda

| Ronda | Duración | Aciertos | Errores color | Timeout | Precisión | Ritmo | Puntuación acumulada | Mejor combo |
|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 2 | 31,71 s | 10 | 1 | 0 | 90,9 % | 18,92 aciertos/min | 4025 | 7 |
| 3 | 28,26 s | 10 | 1 | 0 | 90,9 % | 21,23 aciertos/min | 8600 | 13 |
| 4 | 42,68 s | 10 | 0 | 0 | 100,0 % | 14,06 aciertos/min | 12350 | 13 |

La ronda 3 es la más rápida, con un ritmo de **21,23 aciertos/min**. La ronda 4 es más lenta, pero mantiene una precisión perfecta. La ejecución muestra buen control de la tarea y ausencia de bloqueos temporales.

---

## 4. Secuencia temporal de aciertos

| Ronda | Tiempo medio entre aciertos | Mayor intervalo entre aciertos | Tiempos de acierto desde inicio de ronda |
|---:|---:|---:|---|
| 2 | 3,17 s | 6,53 s | 2,44, 5,30, 7,98, 8,62, 12,66, 14,80, 19,87, 23,95, 30,48, 31,00 |
| 3 | 2,63 s | 5,73 s | 3,94, 6,08, 6,66, 9,91, 10,55, 13,80, 17,69, 18,33, 21,88, 27,62 |
| 4 | 4,07 s | 5,46 s | 5,44, 8,94, 9,58, 14,77, 20,23, 24,13, 29,20, 33,15, 37,56, 42,03 |

En la ronda 3 se observa el patrón más eficiente: los aciertos aparecen más agrupados temporalmente y el intervalo máximo entre aciertos es menor que en la ronda 2. La ronda 4 presenta una ejecución más pausada, con aciertos más espaciados, pero sin errores.

---

## 5. Análisis de errores

| Ronda | Tiempo desde inicio de ronda | Color esperado | Color colocado |
|---:|---:|---|---|
| 2 | 17,13 s | Red | Blue |
| 3 | 22,46 s | Blue | Red |
| 4 | — | — | — |

Los dos errores son errores de selección de color:

- En la ronda 2 se esperaba `Red` y se colocó `Blue`.
- En la ronda 3 se esperaba `Blue` y se colocó `Red`.

No hay timeouts ni interrupciones largas. Esto sugiere que los fallos son puntuales y no comprometen la ejecución general del ejercicio.

---

## 6. Cinemática de la mano derecha

| Ronda | Trayectoria mano derecha | Velocidad media | Velocidad máxima | Percentil 95 velocidad | Rango X | Rango Y | Rango Z |
|---:|---:|---:|---:|---:|---:|---:|---:|
| 2 | 12,25 m | 0,377 m/s | 2,29 m/s | 1,17 m/s | 0,379 m | 0,230 m | 0,434 m |
| 3 | 9,38 m | 0,327 m/s | 1,90 m/s | 0,98 m/s | 0,376 m | 0,291 m | 0,409 m |
| 4 | 11,28 m | 0,263 m/s | 2,37 m/s | 0,87 m/s | 0,362 m | 0,240 m | 0,368 m |

### Interpretación cinemática

La mano derecha recorre un total aproximado de **32,90 m** durante las tres rondas analizadas.

La ronda 2 tiene la mayor trayectoria de mano (**12,25 m**) y también la velocidad media más alta. La ronda 3, pese a ser la más rápida a nivel de juego, presenta menor trayectoria acumulada, lo que indica una ejecución más eficiente. La ronda 4 es más lenta y con menor velocidad media, pero no pierde precisión.

Los rangos espaciales son relativamente estables entre rondas. El rango vertical máximo aparece en la ronda 3, mientras que el rango en profundidad es mayor en la ronda 2.

---

## 7. Movimiento de cabeza y posible compensación

| Ronda | Trayectoria cabeza | Velocidad media cabeza | Velocidad máxima cabeza | Relación cabeza/mano |
|---:|---:|---:|---:|---:|
| 2 | 2,04 m | 0,064 m/s | 0,320 m/s | 16,6 % |
| 3 | 1,47 m | 0,051 m/s | 0,300 m/s | 15,7 % |
| 4 | 1,76 m | 0,041 m/s | 0,345 m/s | 15,6 % |

La trayectoria acumulada de cabeza es de **5,27 m**, con una relación global cabeza/mano de aproximadamente **16,0 %**.

La relación cabeza/mano se mantiene muy estable, alrededor del 15–17 %. No se observa un incremento progresivo de compensación con cabeza/tronco a medida que avanza la ejecución. Esto es positivo, especialmente porque la ronda 4 es más lenta pero no muestra un aumento proporcional de movimiento cefálico.

---

## 8. Calidad de visión y detección

| Ronda | Detecciones | Frecuencia visual aprox. | Red | Blue | Unknown | Conf. Red | Conf. Blue |
|---:|---:|---:|---:|---:|---:|---:|---:|
| 2 | 244 | 7,24 Hz | 99 | 141 | 4 (1,6 %) | 0,678 | 0,701 |
| 3 | 161 | 5,37 Hz | 47 | 95 | 19 (11,8 %) | 0,676 | 0,703 |
| 4 | 246 | 5,52 Hz | 95 | 133 | 18 (7,3 %) | 0,696 | 0,687 |

En total se registran **651 detecciones visuales**, de las cuales **41** son `Unknown`, equivalente al **6,3 %**.

La confianza media de detección se mantiene alrededor de 0,68–0,70. La ronda 3 tiene menos detecciones totales y una proporción mayor de `Unknown`, pero esto no impide completar la tarea. La ronda 2 es la que ofrece mayor frecuencia visual estimada.

---

## 9. IMU, fusión y señal FSR

| Ronda | Muestras `cube_state` | Frecuencia fusión aprox. | Grips Red | Grips Blue | Raw max Red | Raw max Blue |
|---:|---:|---:|---:|---:|---:|---:|
| 2 | 1040 | 30,89 Hz | 7 | 1 | 63 | 22 |
| 3 | 934 | 30,93 Hz | 0 | 0 | 8 | 3 |
| 4 | 1380 | 30,87 Hz | 2 | 2 | 16 | 12 |

La frecuencia de fusión/estado de cubos es muy estable, alrededor de **31 Hz**, lo que indica un registro técnico consistente.

La señal FSR aparece poco activada en comparación con la interacción real del ejercicio. Esto no debe interpretarse como un fallo, porque el cubo puede cogerse y manipularse sin presionar necesariamente la zona del sensor. En este caso, la señal FSR debe considerarse una medida complementaria de presión/contacto, no un indicador obligatorio de agarre.

---

## 10. Segmentos de interacción

| Ronda | Segmentos registrados |
|---:|---:|
| 2 | 8 |
| 3 | 0 |
| 4 | 4 |

Se registran **12 segmentos** en total. Sin embargo, algunos tienen duraciones muy breves y trayectoria nula, por lo que conviene no usarlos como fuente principal para caracterizar ciclos completos de manipulación.

Para este análisis, la fuente más fiable para rendimiento es `game_events`, y para movimiento del usuario es `patient_kinematics`.

---

## 11. Calibración

| Ronda | Error abs. medio Red | Error abs. medio Blue | Error sim. medio Red | Error sim. medio Blue |
|---:|---:|---:|---:|---:|
| 2 | 23,74° | 7,49° | 23,74° | 7,49° |
| 3 | 32,63° | 6,20° | 32,63° | 6,20° |
| 4 | 30,62° | 5,69° | 30,62° | 5,69° |

La calibración muestra un patrón claro:

- `CubeBlue` presenta errores bajos, entre aproximadamente **5,69°** y **7,49°**.
- `CubeRed` presenta errores más altos, entre aproximadamente **23,74°** y **32,63°**.

Esto sugiere que, en esta ejecución, el cubo azul tuvo una orientación estimada más estable que el rojo. Aun así, la tarea se completa correctamente, por lo que la variabilidad del rojo no parece haber impedido el rendimiento funcional.

---

# 12. Conclusiones

## Conclusión funcional

El Terapeuta 2 completa correctamente las tres rondas disponibles, con **30 aciertos**, **2 errores de color**, **0 timeouts** y una precisión global del **100,0 %**. La ejecución es funcionalmente válida y muestra un desempeño alto.

## Conclusión sobre rendimiento

La ronda 3 es la más eficiente en términos de ritmo y trayectoria de la mano. La ronda 4 es más lenta, pero mantiene precisión perfecta. Los dos errores registrados son puntuales y de color, sin evidencias de pérdida de continuidad o bloqueo en la tarea.

## Conclusión cinemática

El movimiento de la mano derecha es consistente y funcional. La trayectoria total registrada es de **32,90 m**. La ronda 3 destaca por combinar rapidez con menor trayectoria, lo que puede interpretarse como mayor eficiencia motora. No se observa un aumento progresivo de compensación mediante movimiento de cabeza.

## Conclusión técnica

El sistema registra de forma estable la fusión/IMU, con una frecuencia aproximada de **31 Hz**. La visión funciona de manera suficiente para completar el ejercicio, aunque aparecen algunas detecciones `Unknown`, especialmente en las rondas 3 y 4. La calibración del cubo azul es buena, mientras que el cubo rojo presenta mayor error angular medio.

## Resumen final

La ejecución del Terapeuta 2 puede considerarse **válida, completa y de alto rendimiento**. El perfil observado es el de una persona que domina la tarea, con precisión elevada, ausencia de timeouts y ritmo alto. Desde el punto de vista técnico, los datos son adecuados para análisis de rendimiento y cinemática, aunque conviene revisar la estabilidad de calibración del cubo rojo y tratar los segmentos de interacción como información secundaria hasta que capturen ciclos completos de manipulación.
