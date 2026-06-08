# Informe del ejercicio de rehabilitación en realidad mixta — Terapeuta 1

## 1. Identificación del registro

Archivo analizado: `SESSION_20260518_111248_R3_RH.zip`

El ZIP contiene cinco carpetas de sesión correspondientes a las rondas `R1` a `R5`, todas realizadas con mano derecha (`RH`). En conjunto, el ejercicio aparece completado, ya que se registra `GameOver` al final de la quinta ronda con `win=True`.

Configuración detectada en el registro inicial:

`hand=Right rounds=5 targets=10`

Por tanto, este informe analiza un ejercicio completo de **5 rondas**, con **10 objetivos por ronda**.

---

## 2. Resumen global

| Métrica global | Resultado |
|---|---:|
| Rondas analizadas | 5 |
| Objetivos completados | 50 |
| Aciertos | 50 |
| Errores de color | 9 |
| Timeouts | 0 |
| Intentos totales | 59 |
| Precisión global | 84.7 % |
| Puntuación final | 15875 |
| Mejor combo | 18 |
| Tiempo efectivo total de rondas | 180.52 s |
| Ritmo medio efectivo | 16.62 aciertos/min |
| Tiempo total de juego indicado por `GameOver` | 03:12 |

El ejercicio puede considerarse **completo y funcionalmente válido**: se alcanzan los 50 objetivos previstos y se registra finalización correcta del juego.

---

## 3. Resultados por ronda

| Ronda | Duración efectiva | Aciertos | Errores | Precisión | Ritmo | Puntuación acumulada | Mejor combo |
|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | 46.54 s | 10 | 1 | 90.9 % | 12.89 aciertos/min | 2025 | 6 |
| 2 | 35.33 s | 10 | 0 | 100.0 % | 16.98 aciertos/min | 7275 | 14 |
| 3 | 34.62 s | 10 | 4 | 71.4 % | 17.33 aciertos/min | 11625 | 18 |
| 4 | 31.50 s | 10 | 2 | 83.3 % | 19.05 aciertos/min | 13775 | 18 |
| 5 | 32.53 s | 10 | 2 | 83.3 % | 18.45 aciertos/min | 15875 | 18 |


La evolución muestra una mejora clara después de la primera ronda. La ronda 2 es la única ronda sin errores y mantiene una secuencia larga de aciertos. La ronda 4 es la más rápida en ritmo efectivo, aunque contiene dos errores. La ronda 3 es la menos precisa, con cuatro errores de color.

---

## 4. Evolución del rendimiento

La primera ronda muestra un arranque más lento: el primer acierto llega aproximadamente a los **9,87 s** desde el inicio de ronda. A partir de la ronda 2, el primer acierto aparece mucho antes, entre **1,84 s y 3,26 s**, lo que indica familiarización rápida con la tarea.

| Ronda | Primer acierto desde inicio | Tiempo medio entre aciertos | Mayor intervalo entre aciertos |
|---:|---:|---:|---:|
| 1 | 9.87 s | 4.00 s | 6.03 s |
| 2 | 2.69 s | 3.55 s | 7.39 s |
| 3 | 1.84 s | 3.57 s | 6.01 s |
| 4 | 3.26 s | 3.07 s | 4.46 s |
| 5 | 2.33 s | 3.28 s | 5.44 s |

La progresión más clara es la siguiente:

- La **ronda 1** presenta mayor latencia inicial y una precisión buena, pero no óptima.
- La **ronda 2** es la más limpia, con **100 % de precisión** y sin errores.
- La **ronda 3** concentra la mayor cantidad de errores, todos del mismo tipo: se esperaba rojo y se colocó azul.
- La **ronda 4** es la más rápida en ritmo, pero incluye dos errores al usar rojo cuando se esperaba azul.
- La **ronda 5** mantiene buen ritmo y cierra el ejercicio con 10 aciertos, aunque con dos errores.

---

## 5. Secuencia de aciertos y errores

En la tabla siguiente, `R` representa cubo rojo y `B` representa cubo azul.

| Ronda | Secuencia de aciertos | Errores principales |
|---:|---|---|
| 1 | R → B → R → B → B → R → R → R → R → B | Red->Blue |
| 2 | R → B → R → R → B → B → R → R → R → R | Sin errores |
| 3 | R → B → B → R → R → R → B → R → R → R | Red->Blue, Red->Blue, Red->Blue, Red->Blue |
| 4 | B → B → B → B → B → B → B → B → B → B | Blue->Red, Blue->Red |
| 5 | R → R → R → R → B → B → R → R → B → B | Red->Blue, Red->Blue |


Detalle de errores de color:

| Ronda | Tiempo en ronda aprox. | Esperado | Colocado | Comentario |
|---:|---:|---|---|---|
| 1 | 29.12 s | Red | Blue | Error de color |
| 3 | 10.34 s | Red | Blue | Error de color |
| 3 | 11.64 s | Red | Blue | Error de color |
| 3 | 26.60 s | Red | Blue | Error de color |
| 3 | 29.32 s | Red | Blue | Error de color |
| 4 | 11.66 s | Blue | Red | Error de color |
| 4 | 30.27 s | Blue | Red | Error de color |
| 5 | 2.97 s | Red | Blue | Error de color |
| 5 | 10.16 s | Red | Blue | Error de color |


El patrón de errores no parece aleatorio. En las rondas 1, 3 y 5 predominan errores en los que se esperaba **rojo** y se colocó **azul**. En la ronda 4 ocurre lo contrario: se esperaba **azul** y se colocó **rojo**. La ronda 2 no presenta errores.

---

## 6. Cinemática de la mano derecha

| Ronda | Trayectoria mano der. | Vel. media mano | Vel. máx. mano | P95 vel. mano | Trayectoria cabeza | Relación cabeza/mano |
|---:|---:|---:|---:|---:|---:|---:|
| 1 | 10.23 m | 0.216 m/s | 1.72 m/s | 0.85 m/s | 1.43 m | 14.0 % |
| 2 | 8.65 m | 0.242 m/s | 2.02 m/s | 0.79 m/s | 0.80 m | 9.2 % |
| 3 | 10.68 m | 0.305 m/s | 2.17 m/s | 0.90 m/s | 0.77 m | 7.2 % |
| 4 | 9.45 m | 0.294 m/s | 2.18 m/s | 0.88 m/s | 0.71 m | 7.5 % |
| 5 | 10.08 m | 0.305 m/s | 2.24 m/s | 0.91 m/s | 0.70 m | 7.0 % |


La mano derecha recorre en total aproximadamente **49.10 m** durante el ejercicio. La velocidad media global, estimada a partir de las medias por ronda, se mantiene en un rango funcional de aproximadamente **0,22–0,31 m/s**.

La ronda 1 tiene la menor velocidad media y la mayor duración, lo que encaja con una fase inicial de adaptación. Desde la ronda 2 en adelante, el movimiento de la mano es más eficiente en tiempo, con ritmos superiores.

El percentil 95 de velocidad se mantiene por debajo de **0,91 m/s** en todas las rondas, lo que indica que las velocidades habituales son estables. Las velocidades máximas, entre **1,72 y 2,24 m/s**, son picos puntuales y no describen el movimiento típico.

---

## 7. Rango espacial de movimiento de la mano

| Ronda | Rango X mano | Rango Y mano | Rango Z mano |
|---:|---:|---:|---:|
| 1 | 0.319 m | 0.216 m | 0.469 m |
| 2 | 0.335 m | 0.283 m | 0.282 m |
| 3 | 0.384 m | 0.241 m | 0.285 m |
| 4 | 0.317 m | 0.224 m | 0.240 m |
| 5 | 0.412 m | 0.282 m | 0.268 m |


El rango de trabajo de la mano derecha se mantiene bastante estable. La mayor amplitud lateral aparece en la ronda 5, mientras que la mayor amplitud vertical aparece en la ronda 2. El rango en profundidad es mayor en la ronda 1, probablemente por exploración inicial, ajuste de posición o mayor recorrido en los primeros objetivos.

---

## 8. Movimiento de cabeza y posibles compensaciones

La trayectoria acumulada de cabeza durante todo el ejercicio es de aproximadamente **4.41 m**, frente a **49.10 m** de la mano derecha. La relación global cabeza/mano es de **9.0 %**.

Esta relación es relativamente baja y disminuye claramente después de la primera ronda. Esto sugiere que el movimiento principal recae en la extremidad superior derecha y que no hay evidencia fuerte de compensación progresiva mediante cabeza o tronco superior. Con los datos disponibles no puede evaluarse directamente el tronco, pero la señal de cabeza no apunta a una compensación dominante.

---

## 9. Calidad de visión y detección

| Ronda | Detecciones | Red | Blue | Unknown | Unknown | Frec. visual | Conf. Red | Conf. Blue | Keypoints visibles |
|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | 433 | 202 | 223 | 8 | 1.8 % | 8.84 Hz | 0.694 | 0.707 | 100.0 % |
| 2 | 310 | 133 | 171 | 6 | 1.9 % | 8.32 Hz | 0.694 | 0.711 | 100.0 % |
| 3 | 319 | 160 | 157 | 2 | 0.6 % | 8.74 Hz | 0.701 | 0.711 | 100.0 % |
| 4 | 264 | 118 | 124 | 22 | 8.3 % | 7.91 Hz | 0.716 | 0.706 | 100.0 % |
| 5 | 300 | 149 | 150 | 1 | 0.3 % | 8.72 Hz | 0.705 | 0.713 | 100.0 % |


La visión funciona de forma estable durante el ejercicio:

- Se registran **1626 detecciones** en total.
- La frecuencia visual media es de aproximadamente **8.50 Hz**.
- Solo **39 detecciones** aparecen como `Unknown`, lo que representa aproximadamente **2.4 %** del total.
- El porcentaje de detecciones con los cuatro keypoints visibles es del **100 %** en todas las rondas.

La ronda 4 es la que presenta más detecciones `Unknown`, con 22 casos. Aun así, el sistema mantiene detecciones suficientes para completar correctamente la ronda.

---

## 10. IMU, fusión, FSR y segmentos

| Ronda | Muestras estado/fusión | Frec. aprox. | Grip Red | Grip Blue | Raw Red máx. | Raw Blue máx. | Segmentos |
|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | 1538 | 31.14 Hz | 0 | 2 | 4 | 11 | 2 |
| 2 | 1156 | 30.93 Hz | 16 | 17 | 47 | 86 | 33 |
| 3 | 1136 | 30.95 Hz | 15 | 15 | 65 | 64 | 30 |
| 4 | 1038 | 30.97 Hz | 12 | 68 | — | — | — |
| 5 | 1068 | 30.91 Hz | 15 | 6 | 65 | 160 | 21 |


La frecuencia de estado/fusión es muy estable, en torno a **30.98 Hz**. Esto indica una adquisición homogénea de datos de seguimiento durante todo el ejercicio.

Sobre el FSR, debe mantenerse la misma interpretación indicada para otros pacientes: **no es necesario tocar el FSR para coger o manipular el cubo**. Por tanto, la ausencia de activación FSR no implica ausencia de agarre. En este caso sí aparecen activaciones claras a partir de la ronda 2, especialmente en el cubo azul en la ronda 4 y en el cubo rojo en varias rondas.

Respecto a `interaction_segments`, el archivo no debe usarse como fuente principal de análisis de transporte o manipulación completa. En varias rondas los segmentos tienen duraciones muy cortas y longitud de trayectoria limitada o nula. Además, en la ronda 4 el archivo de segmentos está vacío/no parseable. Para el análisis funcional y cinemático es más fiable usar `game_events`, `patient_kinematics`, `vision_data` y `fusion_result`.

---

## 11. Calibración

| Ronda | Red abs. | Red sim. | Blue abs. | Blue sim. |
|---:|---:|---:|---:|---:|
| 1 | 7.74° | 7.74° | 12.48° | 12.48° |
| 2 | 12.39° | 12.39° | 11.20° | 11.20° |
| 3 | 24.19° | 22.90° | 27.69° | 27.69° |
| 4 | —° | —° | —° | —° |
| 5 | 13.02° | 13.02° | 24.75° | 24.75° |


La calibración es buena en las dos primeras rondas, con errores medios en torno a **8–12°**. En la ronda 3 aumenta el error de ambos cubos, especialmente el azul. En la ronda 5 el rojo vuelve a valores moderados, pero el azul mantiene un error medio más alto.

La ronda 4 no contiene archivo `calibration_log.csv`, por lo que no se puede evaluar su calibración angular con el mismo criterio.

En conjunto, la calibración es aceptable para completar la tarea, pero la estabilidad angular empeora en la segunda mitad del ejercicio, especialmente en el cubo azul.

---

## 12. Incidencias de registro

Se detectan las siguientes incidencias técnicas:

1. La ronda 4 no contiene `calibration_log.csv`, `cube_state.csv` ni `sensor_imu.csv`; sí contiene `fusion_result.csv`, `game_events.csv`, `patient_kinematics.csv`, `vision_data.csv` y `vision_data_all.csv`.
2. El archivo `interaction_segments.csv` de la ronda 4 está vacío o no contiene columnas parseables.
3. Los segmentos de interacción no representan de forma robusta ciclos completos de coger, transportar y soltar.

Estas incidencias no invalidan el análisis funcional del ejercicio, porque los eventos de juego y la cinemática sí están disponibles.

---

# Conclusiones

## Conclusión funcional

El Terapeuta 1 completa correctamente el ejercicio completo de 5 rondas y 50 objetivos. La precisión global es de **84.7 %**, con **9 errores de color** y **0 timeouts**. El resultado funcional es alto, especialmente porque se completa la tarea sin interrupciones relevantes y con una puntuación final de **15875 puntos**.

## Conclusión sobre rendimiento

El rendimiento mejora claramente tras la primera ronda. La ronda 2 es la más precisa, con 10 aciertos y ningún error. La ronda 3 concentra el mayor número de errores, pero el usuario mantiene un ritmo alto y completa igualmente los 10 objetivos. La ronda 4 es la más rápida en términos de aciertos/minuto.

El mejor combo alcanza **18**, lo que refleja una secuencia prolongada de aciertos consecutivos y buena adaptación a la dinámica del ejercicio.

## Conclusión cinemática

La mano derecha realiza una trayectoria acumulada de aproximadamente **49.10 m**, con velocidades medias moderadas y estables. El movimiento de cabeza es bajo en relación con el movimiento de la mano, con una relación global de **9.0 %**, por lo que no se observan indicios claros de compensación creciente mediante cabeza.

## Conclusión técnica

El registro visual y la fusión son estables. La visión mantiene una frecuencia cercana a **8,5 Hz**, mientras que la fusión se mantiene alrededor de **31 Hz**. El sistema detecta los cubos con confianza media cercana a **0,70** y con keypoints completos en las detecciones registradas.

Los principales aspectos técnicos a revisar son la ausencia parcial de archivos en la ronda 4, la utilidad limitada de `interaction_segments` y la variabilidad de calibración angular en rondas posteriores, especialmente para el cubo azul.

## Resumen final

El ejercicio del Terapeuta 1 es una ejecución completa, válida y de buen rendimiento. El usuario muestra rápida adaptación tras la primera ronda, alta capacidad para completar los objetivos y ausencia de timeouts. Los errores observados parecen deberse principalmente a selección puntual del color incorrecto, no a incapacidad para completar la tarea. Desde el punto de vista técnico, los datos son suficientes para analizar rendimiento, cinemática y calidad de tracking, aunque conviene mejorar la consistencia de los archivos generados y el registro de segmentos de interacción.
