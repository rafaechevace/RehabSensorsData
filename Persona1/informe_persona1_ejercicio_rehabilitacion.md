# Informe del ejercicio de rehabilitación en realidad mixta — Persona 1

## 1. Alcance del análisis

Se ha analizado el ZIP `SESSION_20260518_122232_R2_RH.zip`, que contiene registros CSV de varias ejecuciones del ejercicio con mano derecha (`RH`). En el ZIP aparecen datos completos de las rondas **1**, **2** y una ejecución de **ronda 4**. No aparece una carpeta independiente con los CSV de la ronda 3, aunque los contadores acumulados al inicio de la ronda 4 indican que esa ronda 3 sí debió ejecutarse y completarse previamente.

Por tanto, el informe distingue entre:

- **Rondas con CSV completos:** R1, R2 y R4.

- **Ronda inferida por contadores acumulados:** R3, con 10 aciertos y 0 fallos, pero sin cinemática/visión/calibración específica disponible.

- **Ronda 4:** ejecución incompleta, con interrupción larga y timeouts; no debe compararse directamente con las rondas completadas.

## 2. Resumen global

| Métrica | Resultado |
|---|---:|
| Mano utilizada | Derecha |
| Rondas completas con CSV | 2: R1 y R2 |
| Ronda inferida sin CSV específico | R3 |
| Ronda incompleta con CSV | R4 |
| Aciertos acumulados al final de R2 | 20 |
| Aciertos acumulados al inicio de R4 | 30 |
| Aciertos acumulados al final del registro | 39 |
| Fallos acumulados al final del registro | 4 |
| Puntuación final registrada | 38950 |
| Mejor combo registrado | 38 |
| Precisión acumulada final, hits/(hits+misses) | 90,7 % |

La ejecución del paciente es muy buena en las rondas completadas: las rondas 1 y 2 tienen **10/10 aciertos y 0 errores**, y la ronda 3 parece haber añadido otros **10 aciertos sin fallos** según los contadores acumulados. La ronda 4 se interrumpe y queda incompleta, por lo que debe analizarse como una ejecución parcial o no comparable.

## 3. Resultados por ronda

| Ronda | Estado | Duración registrada | Aciertos | Errores color | Timeouts | Precisión | Puntuación / contador |
|---:|---|---:|---:|---:|---:|---:|---:|
| 1 | Completa | 29,10 s | 10 | 0 | 0 | 100,0 % | 3250 |
| 2 | Completa | 35,65 s | 10 | 0 | 0 | 100,0 % | 11500 |
| 4 | Incompleta | 335,34 s | 9 | 1 | 3 | 69,2 % | 38950 |
| 3 | Inferida, sin CSV específico | — | 10 | 0 | 0 | 100,0 % | incremento +13250 |

Nota: la ronda 3 se ha colocado al final de la tabla porque no existe carpeta de datos propia en el ZIP. Se infiere por la diferencia entre los contadores acumulados al final de R2 y al inicio de R4.

## 4. Interpretación del rendimiento funcional

Las rondas 1 y 2 muestran un rendimiento funcional excelente. En ambas, la persona completa los 10 objetivos sin errores ni timeouts. Además, la progresión del combo es continua: termina la ronda 1 con combo 10 y la ronda 2 con combo 20. Al inicio de la ronda 4 el contador ya marca 30 aciertos, 0 fallos y combo 30, lo que permite inferir que la ronda 3 también fue completada sin errores.

La ronda 4 empieza también muy bien: el paciente alcanza 8 aciertos consecutivos adicionales, llegando a un **combo de 38**. Después aparece un error de color, seguido de varios timeouts y una interrupción larga. Esto sugiere que el problema de la ronda 4 no refleja necesariamente una pérdida progresiva de capacidad motora, sino una incidencia durante la ejecución: pausa, pérdida de continuidad, fatiga, instrucción externa, fallo de atención o interrupción del protocolo.

## 5. Secuencia de eventos relevante

| Ronda | Evento clave | Tiempo |
|---:|---|---:|
| 1 | 10 aciertos consecutivos, sin fallos | 3,31–32,40 s |
| 2 | 10 aciertos consecutivos, sin fallos | 2,08–37,73 s |
| 3 | 10 aciertos inferidos por contadores, sin fallos | sin CSV específico |
| 4 | 8 aciertos iniciales consecutivos | 2,12–27,93 s |
| 4 | Error de color: esperaba rojo y colocó azul | 28,57 s |
| 4 | Timeout esperando rojo | 40,46 s |
| 4 | Timeout tras una interrupción larga | 325,21 s |
| 4 | Acierto posterior con rojo | 325,88 s |
| 4 | Timeout esperando azul | 337,42 s |

Entre el timeout de `40,46 s` y el siguiente evento en `325,21 s` hay una pausa de aproximadamente **284,75 s**. Esta interrupción distorsiona las métricas temporales, de velocidad media y frecuencia aparente de los sensores en la ronda 4.

## 6. Cinemática de la mano derecha

| Ronda | Muestras | Trayectoria mano derecha | Velocidad media | Velocidad máxima | Percentil 95 velocidad | Rango X | Rango Y | Rango Z |
|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | 494 | 7,20 m | 0,223 m/s | 3,57 m/s | 0,87 m/s | 0,34 m | 0,11 m | 0,42 m |
| 2 | 582 | 8,28 m | 0,220 m/s | 1,93 m/s | 0,84 m/s | 0,45 m | 0,13 m | 0,34 m |
| 4 | 1177 | 24,57 m | 0,071 m/s | 23,88 m/s | 1,10 m/s | 0,46 m | 1,19 m | 0,57 m |

En las dos rondas completas con CSV, la cinemática es bastante estable. La mano derecha recorre **7,20 m** en R1 y **8,28 m** en R2, con velocidades medias muy próximas, alrededor de **0,22 m/s**. El percentil 95 de velocidad también es similar, entre **0,84 y 0,87 m/s**, lo que indica un patrón de movimiento bastante consistente.

La ronda 4 muestra una trayectoria mayor, **24,57 m**, pero esta cifra debe interpretarse con cautela porque incluye una interrupción larga y posibles movimientos no directamente asociados a la tarea. La velocidad máxima de R4, **23,88 m/s**, es claramente artefactual o no fisiológica para una tarea de manipulación de cubos; por tanto, no debe usarse como indicador clínico. El percentil 95, **1,10 m/s**, es más robusto y queda en un rango más comparable con las rondas previas.

## 7. Movimiento de cabeza y posibles compensaciones

| Ronda | Trayectoria cabeza | Velocidad media cabeza | Relación cabeza/mano |
|---:|---:|---:|---:|
| 1 | 0,82 m | 0,026 m/s | 11,4 % |
| 2 | 1,06 m | 0,028 m/s | 12,7 % |
| 4 | 4,03 m | 0,012 m/s | 16,4 % |

En R1 y R2 la trayectoria de cabeza es baja, **0,82 m** y **1,06 m**, con una relación cabeza/mano próxima al **11–13 %**. Esto sugiere que la ejecución se basa principalmente en movimiento de mano/brazo, sin una compensación excesiva de cabeza.

En R4 la relación cabeza/mano sube al **16,4 %**, pero esta ronda está contaminada por interrupciones y valores atípicos. No debería utilizarse como evidencia fuerte de compensación clínica creciente sin revisar visualmente el registro o segmentar únicamente los periodos activos.

## 8. Calidad de visión y detección

| Ronda | Detecciones | Frecuencia visual aprox. | Red | Blue | Unknown | Unknown % | Conf. Red | Conf. Blue | Keypoints visibles |
|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | 274 | 8,77 Hz | 106 | 155 | 13 | 4,7 % | 0,706 | 0,712 | 100,0 % |
| 2 | 302 | 8,04 Hz | 148 | 149 | 5 | 1,7 % | 0,702 | 0,718 | 100,0 % |
| 4 | 504 | 1,46 Hz | 230 | 259 | 15 | 3,0 % | 0,696 | 0,717 | 100,0 % |

La visión funciona de forma sólida en R1 y R2, con frecuencias aproximadas de **8,77 Hz** y **8,04 Hz**. La proporción de detecciones `Unknown` es baja, especialmente en R2. Las confianzas medias de detección se sitúan alrededor de **0,70–0,72**, y los keypoints aparecen visibles en el **100 %** de las detecciones registradas.

En R4 la frecuencia aparente baja a **1,46 Hz**, pero esto se debe principalmente a que la duración total incluye una pausa muy larga. No implica necesariamente que el detector funcione peor durante los periodos activos.

## 9. IMU, fusión y FSR

| Ronda | Muestras cube/fusion | Frecuencia aprox. | Grip Blue | Grip Red | Raw max Blue | Raw max Red |
|---:|---:|---:|---:|---:|---:|---:|
| 1 | 986 | 30,74 Hz | 20 | 37 | 37 | 97 |
| 2 | 1164 | 30,90 Hz | 12 | 4 | 48 | 66 |
| 4 | 2356 | 6,77 Hz | 19 | 26 | 185 | 90 |

La frecuencia de registro de fusión/estado de cubos es estable en R1 y R2, alrededor de **30,7–30,9 Hz**. En R4 baja artificialmente por la interrupción larga incluida en el registro.

La señal FSR debe interpretarse como información complementaria de presión/contacto, no como condición obligatoria para validar el agarre. En este paciente sí hay activaciones claras del FSR en varias rondas, especialmente en R1, pero la validez funcional del ejercicio se determina mejor por los eventos del juego y la trayectoria de la mano.

## 10. Segmentos de interacción

| Ronda | Segmentos registrados | Segmentos con duración > 0 |
|---:|---:|---:|
| 1 | 57 | 57 |
| 2 | 16 | 16 |
| 4 | 45 | 45 |

A diferencia de otros registros, aquí sí aparecen segmentos de interacción en las tres carpetas analizadas. Sin embargo, muchos segmentos tienen duraciones muy pequeñas y longitud de trayectoria nula o casi nula, por lo que todavía conviene tratarlos con cautela. Para el análisis funcional y cinemático global son más robustos `game_events`, `patient_kinematics`, `vision_data`, `cube_state` y `fusion_result`.

## 11. Calibración

| Ronda | Error abs. medio Blue | Error sim. medio Blue | Error abs. medio Red | Error sim. medio Red |
|---:|---:|---:|---:|---:|
| 1 | 6,40° | 6,40° | 12,92° | 12,92° |
| 2 | 11,05° | 11,05° | 25,27° | 25,27° |
| 4 | 4,70° | 4,70° | 70,81° | 19,06° |

La calibración del cubo azul es muy buena en R1 y R4, con errores medios bajos. En R2 sube, pero sigue siendo moderada. El cubo rojo muestra más variabilidad: R1 es aceptable, R2 empeora y R4 presenta un error absoluto medio muy alto (**70,81°**), aunque el error simétrico baja a **19,06°**. Esto sugiere un problema de orientación bruta o ambigüedad por simetría más que una pérdida completa de seguimiento.

## 12. Conclusiones

1. **Rendimiento funcional muy alto en las rondas completadas.** R1 y R2 se completan con 10/10 aciertos y 0 fallos. La ronda 3, aunque no tiene carpeta propia de CSV, se infiere también como completada con 10 aciertos y 0 fallos.

2. **La persona mantiene una secuencia prolongada sin errores.** Antes del primer fallo de R4 se alcanza un combo de 38, lo que indica muy buena continuidad de ejecución, atención y comprensión de la tarea durante la mayor parte del ejercicio.

3. **La ronda 4 no debe compararse directamente con R1 y R2.** Está incompleta e incluye una interrupción larga de aproximadamente 284,75 s. Sus métricas temporales, velocidades medias y frecuencias aparentes quedan distorsionadas.

4. **La cinemática de R1 y R2 es estable.** La mano derecha recorre entre 7,20 y 8,28 m, con velocidad media cercana a 0,22 m/s y sin evidencia clara de compensación excesiva de cabeza.

5. **La visión es suficientemente estable en las rondas válidas.** Las detecciones mantienen confianzas medias alrededor de 0,70 y keypoints visibles en el 100 % de las detecciones registradas.

6. **El FSR no debe usarse como criterio único de agarre.** En este ejercicio aporta información complementaria, pero la ejecución funcional está mejor reflejada por aciertos, errores, cinemática y estado fusionado del cubo.

7. **El principal punto técnico a revisar es la calibración/orientación del cubo rojo**, especialmente en R4, donde el error absoluto aumenta mucho aunque el error simétrico queda más contenido.

## 13. Resumen final

La Persona 1 muestra una ejecución funcionalmente muy buena del ejercicio de rehabilitación en realidad mixta. Las rondas válidas disponibles presentan precisión perfecta y una progresión sostenida del combo. La persona utiliza la mano derecha con un patrón cinemático estable en las rondas completadas, sin indicios claros de compensación excesiva de cabeza. El sistema registra adecuadamente eventos, cinemática, visión e IMU/fusión. La ronda 4 debe marcarse como incompleta o no comparable por la presencia de una interrupción larga y varios timeouts posteriores. Para análisis clínico o comparativo, se recomienda usar principalmente R1, R2 y la información acumulada que permite inferir R3, dejando R4 como incidencia o ejecución parcial.
