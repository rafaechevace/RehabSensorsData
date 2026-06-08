# Informe del ejercicio completo — Paciente 2

Archivo analizado: `SESSION_20260518_121205_R2_RH.zip`.

El ZIP contiene tres carpetas de sesión:

- `SESSION_20260518_121113_R1_RH`
- `SESSION_20260518_121205_R2_RH`
- `SESSION_20260518_121317_R3_RH`

La configuración registrada al inicio es:

`hand=Right rounds=5 targets=10`

Por tanto, el ejercicio estaba previsto para mano derecha, 5 rondas y 10 objetivos por ronda. En los datos disponibles hay tres rondas registradas. Las rondas 1 y 2 aparecen completadas. La ronda 3 queda incompleta y presenta una interrupción temporal grande.

---

## 1. Resumen ejecutivo

El Paciente 2 completa correctamente las dos primeras rondas, con 20 objetivos alcanzados de 20. La tercera ronda no se completa: se registran 7 aciertos, 4 errores de color y 3 timeouts. Además, en la tercera ronda aparece una pausa o discontinuidad de aproximadamente 346,6 s entre bloques de datos, por lo que esta ronda debe interpretarse con cautela y no es comparable directamente con las dos primeras.

Resumen global de los datos disponibles:

| Métrica global | Resultado |
|---|---:|
| Rondas registradas | 3 |
| Rondas completadas | 2 |
| Rondas incompletas | 1 |
| Aciertos totales registrados | 27 |
| Errores de color | 6 |
| Timeouts | 4 |
| Intentos totales registrados | 37 |
| Precisión global sobre todos los intentos | 73,0 % |
| Puntuación final registrada | 6600 |
| Mejor combo registrado | 10 |
| Trayectoria total de mano derecha | 56,65 m |
| Trayectoria total de cabeza | 9,81 m |
| Tiempo cinemático activo estimado | 207,63 s |
| Tiempo de interrupción detectado | 346,62 s |

La precisión global baja por la tercera ronda incompleta. Si se consideran solo las rondas completadas, el paciente obtiene 20 aciertos, 2 errores de color/timeouts y una precisión de 90,9 %.

---

## 2. Resultados por ronda

| Ronda | Completada | Duración de ronda | Aciertos | Errores color | Timeouts | Precisión | Puntuación final | Mejor combo |
|---:|---|---:|---:|---:|---:|---:|---:|---:|
| 1 | Sí | 47,76 s | 10 | 1 | 0 | 90,9 % | 2025 | 6 |
| 2 | Sí | 70,01 s | 10 | 1 | 1 | 83,3 % | 4275 | 8 |
| 3 | No | 420,82 s | 7 | 4 | 3 | 50,0 % | 6600 | 10 |

La ronda 1 tiene buena precisión y se completa en 47,76 s desde el inicio de ronda. La ronda 2 también se completa, pero dura más y contiene un timeout. La ronda 3 no debe considerarse una ronda finalizada: alcanza 7 objetivos y después acumula varios fallos y timeouts.

---

## 3. Interpretación del rendimiento funcional

### Ronda 1

La primera ronda es funcionalmente válida. El paciente alcanza los 10 objetivos con un único error de color.

- 10 aciertos.
- 1 error de color.
- Sin timeouts.
- Precisión: 90,9 %.
- Mejor combo: 6.

El error aparece a los 13,82 s desde el inicio de ronda: se esperaba rojo y se colocó azul.

### Ronda 2

La segunda ronda también es válida, aunque más lenta. El paciente completa los 10 objetivos, pero aparece un error de color y un timeout.

- 10 aciertos.
- 1 error de color.
- 1 timeout.
- Precisión: 83,3 %.
- Mejor combo acumulado: 8.

El timeout se produce cuando el objetivo esperado era rojo. La ronda tiene un periodo de mayor demora antes de continuar, lo que explica parte de la duración superior.

### Ronda 3

La tercera ronda no se completa. Se registran:

- 7 aciertos.
- 4 errores de color.
- 3 timeouts.
- Precisión: 50,0 % sobre los intentos registrados.

Además, se detecta una discontinuidad de aproximadamente 346,6 s en el registro cinemático y de cubos. Esto indica una pausa, interrupción, pérdida de continuidad de la sesión o parada temporal. Por tanto, esta ronda debe marcarse como incompleta o no válida para comparación directa de rendimiento.

---

## 4. Errores y timeouts

| Ronda | Tiempo desde inicio de ronda | Tipo | Color esperado | Color colocado |
|---:|---:|---|---|---|
| 1 | 13,82 s | WrongColor | Red | Blue |
| 2 | 16,08 s | WrongColor | Blue | Red |
| 2 | 44,18 s | Timeout | Red | — |
| 3 | 26,73 s | WrongColor | Red | Blue |
| 3 | 34,16 s | WrongColor | Blue | Red |
| 3 | 37,23 s | WrongColor | Blue | Red |
| 3 | 400,05 s | WrongColor | Blue | Red |
| 3 | 47,08 s | Timeout | Blue | — |
| 3 | 407,09 s | Timeout | Blue | — |
| 3 | 420,82 s | Timeout | Red | — |

En las dos primeras rondas los errores son puntuales. En la tercera ronda aparece una acumulación de errores y timeouts, especialmente con el objetivo azul y hacia el final del registro. Este patrón sugiere que la tercera ronda no representa una ejecución estable del ejercicio.

---

## 5. Cinemática de la mano derecha y movimiento de cabeza

| Ronda | Trayectoria mano derecha | Tiempo activo estimado | Pausas detectadas | Velocidad media activa | Velocidad máxima | Percentil 95 velocidad | Trayectoria cabeza | Relación cabeza/mano |
|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | 9,47 m | 50,79 s | 0,00 s | 0,19 m/s | 1,87 m/s | 0,82 m/s | 2,01 m | 21,2 % |
| 2 | 23,39 m | 71,97 s | 0,00 s | 0,33 m/s | 2,36 m/s | 1,01 m/s | 3,35 m | 14,3 % |
| 3 | 23,79 m | 84,87 s | 346,62 s | 0,28 m/s | 15,23 m/s | 0,98 m/s | 4,45 m | 18,7 % |

La mano derecha recorre:

- Ronda 1: 9,47 m.
- Ronda 2: 23,39 m.
- Ronda 3: 23,79 m.

La trayectoria aumenta claramente en la ronda 2 y se mantiene alta en la ronda 3. Sin embargo, en la tercera ronda hay que tener cuidado: parte del registro está afectado por una discontinuidad temporal y aparecen picos de velocidad muy altos, probablemente artefactos o saltos de tracking. En concreto, la velocidad máxima de la ronda 3 es 15,23 m/s, un valor excesivo para una manipulación normal de cubos.

La relación cabeza/mano es:

- Ronda 1: 21,2 %.
- Ronda 2: 14,3 %.
- Ronda 3: 18,7 %.

No se observa un incremento progresivo claro de compensación de cabeza. La ronda 1 muestra una relación cabeza/mano mayor que las rondas 2 y 3. Aun así, la ronda 3 contiene artefactos y debe interpretarse con cautela.

---

## 6. Rango espacial de movimiento de la mano derecha

| Ronda | Rango X | Rango Y | Rango Z |
|---:|---:|---:|---:|
| 1 | 0,447 m | 0,236 m | 0,538 m |
| 2 | 0,500 m | 0,252 m | 0,554 m |
| 3 | 0,459 m | 1,154 m | 0,731 m |

El rango de trabajo de la mano derecha es amplio en las tres rondas. La ronda 2 muestra una trayectoria total muy alta y un rango espacial similar al de la ronda 1. La ronda 3 muestra un rango vertical anormalmente alto, especialmente en Y, que probablemente está influido por saltos de posición o por la discontinuidad del registro.

---

## 7. Visión y detección de cubos

| Ronda | Detecciones | Frecuencia visual activa | Red | Blue | Unknown | Unknown | Conf. Red | Conf. Blue |
|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | 320 | 8,72 Hz | 146 | 160 | 14 | 4,4 % | 0,694 | 0,696 |
| 2 | 419 | 6,02 Hz | 84 | 326 | 9 | 2,1 % | 0,688 | 0,701 |
| 3 | 545 | 8,22 Hz | 271 | 265 | 9 | 1,7 % | 0,700 | 0,710 |

La visión funciona razonablemente bien en las tres rondas cuando se corrige por tiempo activo. La frecuencia visual activa se mantiene aproximadamente entre 6 y 9 Hz.

Puntos relevantes:

- Todas las detecciones registradas incluyen los 4 keypoints visibles.
- La proporción de `Unknown` es baja globalmente: 32 de 1284 detecciones, aproximadamente 2,5 %.
- La confianza media se mantiene alrededor de 0,69–0,71 para los cubos rojo y azul.
- En la ronda 2 hay una clara predominancia de detecciones del cubo azul, coherente con una secuencia con muchos objetivos azules.

La tercera ronda tiene una frecuencia bruta muy baja si se calcula sobre todo el intervalo temporal, pero esto se debe a la pausa de varios minutos. Al calcular sobre tiempo activo, la frecuencia visual vuelve a valores razonables.

---

## 8. IMU, fusión y FSR

| Ronda | Muestras `cube_state` | Frecuencia activa fusión | CubeRed muestras | CubeBlue muestras | Grip Red | Grip Blue | Raw grip máx. Red | Raw grip máx. Blue |
|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | 1564 | 30,90 Hz | 782 | 782 | 51 | 10 | 67 | 169 |
| 2 | 2230 | 30,99 Hz | 1115 | 1115 | 41 | 7 | 95 | 30 |
| 3 | 2616 | 30,81 Hz | 1308 | 1308 | 0 | 0 | 9 | 8 |

La frecuencia activa de fusión/IMU es muy estable, alrededor de 31 Hz. Esto indica que el registro técnico de cubos es consistente en los periodos activos.

Sobre el FSR:

- Ronda 1: hay activaciones FSR, especialmente en CubeRed.
- Ronda 2: también hay activaciones, aunque moderadas.
- Ronda 3: no hay activaciones de `is_gripping`, y los valores `raw_grip` son bajos.

Como ya se indicó, el FSR no debe usarse como criterio obligatorio de agarre, porque el usuario puede coger el cubo sin presionar la zona sensorizada. En este informe se interpreta como señal complementaria de presión/contacto, no como condición necesaria para validar la manipulación.

---

## 9. Segmentos de interacción

| Ronda | Segmentos | Duración total segmentos | Duración media | Longitud total |
|---:|---:|---:|---:|---:|
| 1 | 61 | 3,290 s | 0,054 s | 0,000 m |
| 2 | 48 | 2,517 s | 0,052 s | 0,000 m |
| 3 | 0 | 0 s | — s | 0 m |

Los segmentos de interacción no parecen capturar trayectorias completas de coger, transportar y soltar. En las rondas 1 y 2 hay muchos segmentos, pero la longitud de trayectoria registrada es 0 m. En la ronda 3 no hay segmentos.

Por tanto, para este paciente tampoco conviene usar `interaction_segments` como fuente principal para analizar calidad del movimiento. Es más fiable usar:

- `game_events` para rendimiento.
- `patient_kinematics` para movimiento del paciente.
- `vision_data` para detección visual.
- `cube_state` y `fusion_result` para seguimiento técnico de cubos.
- `calibration_log` para estabilidad de orientación.

---

## 10. Calibración

| Ronda | Cubo | Muestras | Error absoluto medio | Error simétrico medio | Error absoluto máximo |
|---:|---|---:|---:|---:|---:|
| 1 | CubeRed | 9 | 14,20° | 14,20° | 38,83° |
| 1 | CubeBlue | 9 | 73,00° | 13,70° | 161,80° |
| 2 | CubeRed | 2 | 20,93° | 20,93° | 27,18° |
| 2 | CubeBlue | 15 | 87,03° | 14,96° | 157,86° |
| 3 | CubeRed | 14 | 43,31° | 40,34° | 50,13° |
| 3 | CubeBlue | 17 | 82,20° | 8,81° | 98,62° |

La calibración muestra un patrón claro:

- CubeRed tiene errores moderados en las rondas 1 y 2, pero empeora en la ronda 3.
- CubeBlue tiene errores absolutos medios muy altos en todas las rondas, entre 73° y 87° en las dos primeras y 82° en la tercera.
- Sin embargo, el error simétrico de CubeBlue es bajo, especialmente en la ronda 3, donde baja a 8,81°.

Esto sugiere que el cubo azul presenta una fuerte ambigüedad de orientación en términos absolutos, pero que al considerar simetrías el sistema reduce mucho el error. Es decir, la orientación bruta del cubo azul puede parecer muy desviada, pero parte de esa desviación corresponde probablemente a orientaciones equivalentes por simetría del cubo.

---

## 11. Validez de la sesión

### Rondas válidas

Las rondas 1 y 2 pueden considerarse válidas para análisis funcional:

- Ambas se completan.
- Hay 20 aciertos en total.
- Hay pocos fallos.
- La cinemática y la fusión tienen continuidad temporal.
- La frecuencia IMU/fusión es estable.

### Ronda con validez limitada

La ronda 3 debe marcarse como incompleta o con validez limitada:

- No hay `RoundComplete`.
- Solo se alcanzan 7 de 10 objetivos.
- Hay 4 errores de color y 3 timeouts.
- Existe una discontinuidad temporal de aproximadamente 346,6 s.
- Aparecen picos cinemáticos anómalos.

Por tanto, no debería mezclarse sin control con las rondas 1 y 2 en análisis estadístico de rendimiento. Puede conservarse como registro de incidencia, fatiga, interrupción o fallo de continuidad de sesión, pero no como ronda completada.

---

# Conclusiones

## Conclusión funcional

El Paciente 2 muestra un rendimiento funcional adecuado en las dos primeras rondas, completando 20 objetivos con una precisión conjunta del 90,9 % si se consideran errores de color y timeouts. La primera ronda es la más estable; la segunda es más larga y contiene un timeout, pero también se completa correctamente.

La tercera ronda no puede considerarse completada. Los datos sugieren una interrupción o pérdida de continuidad importante, seguida de varios fallos y timeouts.

## Conclusión cinemática

La mano derecha realiza una trayectoria total registrada de 56,65 m. La ronda 2 presenta la mayor carga motora válida, con 23,39 m de trayectoria y velocidad media activa de 0,33 m/s. La trayectoria de cabeza no aumenta proporcionalmente, por lo que no hay evidencia clara de compensación creciente de cabeza en las rondas válidas.

La ronda 3 contiene valores anómalos, especialmente un pico de velocidad de mano de 15,23 m/s y un rango vertical excesivo. Estos datos deben revisarse antes de utilizarlos como evidencia clínica.

## Conclusión técnica

El sistema registra correctamente eventos, cinemática, visión, cubos e IMU durante las rondas válidas. La fusión/IMU mantiene una frecuencia activa estable de aproximadamente 31 Hz. La visión tiene una frecuencia activa razonable y baja proporción de detecciones desconocidas.

Los principales puntos técnicos a revisar son:

1. La interrupción temporal de la ronda 3.
2. La ausencia de `RoundComplete` en la ronda 3.
3. Los picos cinemáticos anómalos.
4. La calibración absoluta del cubo azul.
5. El uso limitado de `interaction_segments`, que no está registrando trayectorias completas.

## Resumen final

El ejercicio del Paciente 2 debe interpretarse como una sesión con dos rondas válidas y una tercera ronda incompleta. Las dos primeras rondas demuestran que el paciente puede realizar la tarea con la mano derecha, alcanzar los objetivos y mantener una precisión funcional buena. La tercera ronda parece afectada por una interrupción o incidencia, por lo que no debería emplearse como ronda comparable sin anotarla como no válida o incompleta.

