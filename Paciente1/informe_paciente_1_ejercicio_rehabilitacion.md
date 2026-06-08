# Informe del ejercicio completo — Paciente 1

Se han integrado las tres tandas cargadas como una única ejecución del **Paciente 1**, compuesta por las rondas 1, 2 y 3. El ejercicio estaba configurado como:

`hand=Right rounds=5 targets=10`

En los datos disponibles aparecen **3 rondas completadas**, con 10 objetivos por ronda. Por tanto, este informe analiza el ejercicio completo disponible: **30 objetivos registrados**.

---

## 1. Resumen global del ejercicio

| Métrica global | Resultado |
|---|---:|
| Rondas analizadas | 3 |
| Objetivos completados | 30 |
| Aciertos | 30 |
| Errores de color | 5 |
| Timeouts | 1 |
| Intentos totales, incluyendo timeout | 36 |
| Precisión sin contar timeout | 85,7 % |
| Precisión contando timeout como fallo | 83,3 % |
| Puntuación final | 7600 |
| Mejor combo | 9 |
| Tiempo efectivo total de rondas | 133,43 s |
| Ritmo medio | 13,49 aciertos/min |

El paciente completa correctamente los 30 objetivos disponibles. El rendimiento funcional general es bueno, aunque la tercera ronda introduce más dificultad por un inicio problemático con error y timeout.

---

## 2. Resultados por ronda

| Ronda | Duración | Aciertos | Errores color | Timeout | Precisión con timeout | Ritmo |
|---:|---:|---:|---:|---:|---:|---:|
| 1 | 40,60 s | 10 | 1 | 0 | 90,9 % | 14,78 aciertos/min |
| 2 | 38,34 s | 10 | 2 | 0 | 83,3 % | 15,65 aciertos/min |
| 3 | 54,50 s | 10 | 2 | 1 | 76,9 % | 11,01 aciertos/min |

La **ronda 2** es la más rápida, pero con más errores que la primera. La **ronda 3** es claramente la más lenta, principalmente por el timeout inicial, no porque toda la ronda sea lenta.

---

## 3. Evolución del rendimiento

La evolución no es lineal. Hay una primera ronda bastante estable, una segunda ronda más rápida pero menos precisa, y una tercera ronda con mayor dificultad inicial.

| Métrica | Ronda 1 | Ronda 2 | Ronda 3 |
|---|---:|---:|---:|
| Puntuación acumulada | 2425 | 4875 | 7600 |
| Mejor combo | 8 | 8 | 9 |
| Tiempo medio entre aciertos | 3,53 s | 3,91 s | 3,99 s |
| Mayor intervalo entre aciertos | 5,22 s | 9,24 s | 4,16 s |

En la ronda 3 el mayor retraso no aparece entre aciertos, sino antes del primer acierto válido, debido a un error inicial y un timeout. Después de esa fase inicial, el paciente recupera el ritmo.

---

## 4. Análisis de errores

### Errores totales

| Tipo de error | Número |
|---|---:|
| Error de color | 5 |
| Timeout | 1 |

Distribución por ronda:

| Ronda | Errores observados |
|---:|---|
| 1 | 1 error: esperaba rojo y colocó azul |
| 2 | 2 errores: esperaba azul y colocó rojo |
| 3 | 2 errores: esperaba rojo y colocó azul; además 1 timeout esperando rojo |

Hay un patrón interesante: los errores no son simétricos por ronda.

En la ronda 2, el paciente se equivoca dos veces usando el rojo cuando debía usar azul. En la ronda 3 ocurre lo contrario: usa azul cuando debía usar rojo, y además se produce un timeout también esperando rojo.

Esto sugiere que los fallos no se deben necesariamente a incapacidad motora, sino probablemente a momentos puntuales de confusión, cambio de consigna, atención o interpretación del objetivo activo.

---

## 5. Cinemática de la mano derecha

El ejercicio se realiza con la **mano derecha**.

| Métrica | Ronda 1 | Ronda 2 | Ronda 3 | Total |
|---|---:|---:|---:|---:|
| Trayectoria mano derecha | 11,28 m | 12,32 m | 17,69 m | 41,29 m |
| Velocidad media | 0,258 m/s | 0,305 m/s | 0,313 m/s | 0,294 m/s |
| Velocidad máxima | 2,81 m/s | 2,68 m/s | 7,44 m/s | — |
| Percentil 95 velocidad | 1,22 m/s | 1,23 m/s | 1,21 m/s | — |

La trayectoria de la mano aumenta progresivamente:

- Ronda 1: 11,28 m
- Ronda 2: 12,32 m
- Ronda 3: 17,69 m

Esto indica que en la tercera ronda el paciente mueve bastante más la mano. Parte de este aumento puede deberse a la mayor duración de la ronda, pero también puede reflejar más correcciones, exploración, búsqueda del cubo correcto o trayectorias menos directas.

La velocidad máxima de la ronda 3, `7,44 m/s`, parece demasiado alta para una manipulación natural de este tipo. La trataría con cautela, probablemente como pico puntual de tracking, salto de posición o transición brusca registrada. El percentil 95 se mantiene estable en torno a `1,21–1,23 m/s`, lo que indica que la velocidad habitual de movimiento es bastante consistente entre rondas.

---

## 6. Rango espacial de movimiento

| Ronda | Rango X | Rango Y | Rango Z |
|---:|---:|---:|---:|
| 1 | 0,504 m | 0,182 m | 0,430 m |
| 2 | 0,452 m | 0,317 m | 0,512 m |
| 3 | 0,511 m | 0,380 m | 0,530 m |

La amplitud espacial aumenta especialmente en los ejes **Y** y **Z**:

- El rango vertical pasa de `0,182 m` a `0,380 m`.
- El rango en profundidad pasa de `0,430 m` a `0,530 m`.

Esto sugiere que conforme avanza el ejercicio, el paciente explora un volumen de trabajo mayor. Puede interpretarse positivamente como mayor implicación motora, aunque también puede deberse a más correcciones o menor eficiencia.

---

## 7. Movimiento de cabeza y posibles compensaciones

| Métrica | Ronda 1 | Ronda 2 | Ronda 3 |
|---|---:|---:|---:|
| Trayectoria cabeza | 2,04 m | 1,93 m | 2,73 m |
| Velocidad media cabeza | 0,047 m/s | 0,048 m/s | 0,048 m/s |
| Relación cabeza/mano | 18,1 % | 15,6 % | 15,4 % |

Aunque la cabeza recorre más distancia en la ronda 3, la relación entre movimiento de cabeza y movimiento de mano no aumenta. De hecho, baja ligeramente.

Esto es importante: el aumento de trayectoria de la mano no parece acompañado de una compensación proporcional de cabeza. En principio, no hay evidencia clara de que el paciente esté compensando cada vez más con el tronco/cabeza. Para confirmarlo clínicamente sería necesario analizar también tronco, hombro o postura, pero con estos datos la señal no apunta a una compensación creciente evidente.

---

## 8. Calidad de visión y detección

| Métrica | Ronda 1 | Ronda 2 | Ronda 3 |
|---|---:|---:|---:|
| Detecciones totales | 364 | 318 | 425 |
| Frecuencia visual aprox. | 8,56 Hz | 7,91 Hz | 7,54 Hz |
| Detecciones Red | 173 | 138 | 168 |
| Detecciones Blue | 183 | 142 | 236 |
| Detecciones Unknown | 8 | 38 | 21 |
| Confianza media Red | 0,695 | 0,663 | 0,680 |
| Confianza media Blue | 0,703 | 0,703 | 0,702 |

La detección visual funciona de forma razonablemente estable. El cubo azul mantiene una confianza media muy consistente, alrededor de `0,70`. El cubo rojo baja en la segunda ronda y se recupera parcialmente en la tercera.

El porcentaje global de detecciones `Unknown` es aproximadamente `6,05 %`. La ronda 2 es la peor en este aspecto, con 38 detecciones desconocidas. Esto puede estar relacionado con oclusiones, poses ambiguas, distancia, iluminación, encuadre o momentos en los que el cubo se ve parcialmente.

Un punto positivo: en las detecciones registradas aparecen visibles los 4 keypoints, por lo que cuando el sistema detecta el cubo, la información geométrica parece completa.

---

## 9. IMU, fusión y estado de los cubos

| Métrica | Ronda 1 | Ronda 2 | Ronda 3 |
|---|---:|---:|---:|
| Muestras `cube_state` | 1352 | 1254 | 1770 |
| Frecuencia total aprox. | 31,07 Hz | 31,08 Hz | 31,33 Hz |
| Frecuencia por cubo | ~15,5 Hz | ~15,5 Hz | ~15,7 Hz |

La parte IMU/fusión es estable en frecuencia. Esto es positivo desde el punto de vista técnico: el sistema mantiene un registro continuo y homogéneo.

Sobre el FSR:

| Ronda | Muestras agarre Red | Muestras agarre Blue | Máx. raw Red | Máx. raw Blue |
|---:|---:|---:|---:|---:|
| 1 | 2 | 0 | 16 | 6 |
| 2 | 0 | 0 | 4 | 10 |
| 3 | 38 | 5 | 39 | 15 |

Dado que **no es necesario tocar el FSR para coger el cubo**, estos valores no deben interpretarse como “no ha agarrado”. La manipulación está demostrada por los eventos del juego. El FSR solo indica momentos en los que el usuario sí presionó o tocó de forma suficiente la zona instrumentada.

La ronda 3 muestra más activaciones FSR, especialmente en el cubo rojo, probablemente porque en esa parte se le indicó explícitamente que lo hiciera o porque el agarre coincidió más con la zona del sensor.

---

## 10. Segmentos de interacción

| Ronda | Segmentos registrados |
|---:|---:|
| 1 | 2 |
| 2 | 0 |
| 3 | 43 |

Aquí hay una diferencia fuerte entre rondas. Sin embargo, los segmentos registrados tienen duraciones muy pequeñas y longitud de trayectoria 0 en muchos casos. Esto sugiere que el archivo `interaction_segments` no está representando todavía ciclos completos de manipulación tipo:

`coger → transportar → colocar`

Más bien parece capturar eventos muy puntuales de colocación o cambios instantáneos de estado.

Por tanto, para este informe no usaría `interaction_segments` como fuente principal para analizar calidad del movimiento. Es más fiable apoyarse en:

- `game_events` para rendimiento.
- `patient_kinematics` para movimiento del paciente.
- `vision_data` para calidad visual.
- `cube_state` / `fusion_result` para seguimiento técnico de cubos.
- `calibration_log` para estabilidad de orientación.

---

## 11. Calibración

| Ronda | Error abs. medio Red | Error abs. medio Blue | Error sim. medio Red | Error sim. medio Blue |
|---:|---:|---:|---:|---:|
| 1 | 7,73° | 66,75° | 7,73° | 22,20° |
| 2 | 10,26° | 59,10° | 10,26° | 20,73° |
| 3 | 42,03° | 33,41° | 32,05° | 31,38° |

La calibración cambia claramente entre rondas.

En las dos primeras rondas:

- El cubo rojo está bien calibrado.
- El cubo azul tiene un error absoluto alto, pero el error simétrico baja mucho.

Esto apunta a una ambigüedad de orientación del cubo azul, probablemente relacionada con la simetría del objeto.

En la tercera ronda:

- Mejora el error absoluto del azul.
- Empeora notablemente el rojo.
- Los errores simétricos de ambos cubos quedan alrededor de 31–32°.

Esto indica que la tercera ronda tiene peor estabilidad de orientación, o al menos una calibración menos consistente. Aun así, el ejercicio funcional se completa.

---

# Conclusiones principales

## Conclusión funcional

El Paciente 1 completa las tres rondas disponibles con **30 aciertos de 30 objetivos**, una precisión global del **83,3 % si se incluye el timeout** y una puntuación final de **7600 puntos**. El mejor combo alcanza **9**, lo que indica capacidad para mantener secuencias correctas prolongadas.

Desde el punto de vista funcional, el ejercicio puede considerarse **válido y completado satisfactoriamente**.

---

## Conclusión sobre rendimiento

La primera ronda es la más equilibrada: buena precisión y ritmo estable. La segunda ronda es la más rápida, pero con más errores. La tercera ronda es la más lenta debido a un inicio problemático con error y timeout, aunque después el paciente recupera un ritmo razonable.

El patrón general sugiere que el paciente puede ejecutar correctamente la tarea, pero presenta momentos puntuales de confusión con el color objetivo, especialmente cuando debe cambiar o mantener la selección correcta bajo presión temporal.

---

## Conclusión cinemática

La mano derecha recorre un total de **41,29 m** durante las tres rondas. La trayectoria aumenta de forma progresiva, especialmente en la tercera ronda.

Esto puede interpretarse como:

- Mayor implicación motora.
- Mayor exploración del espacio de trabajo.
- Más correcciones durante la tarea.
- Posible menor eficiencia en la tercera ronda.

No se observa una evidencia clara de compensación creciente de cabeza, porque la relación cabeza/mano disminuye ligeramente de la ronda 1 a la 3.

---

## Conclusión técnica

El sistema registra adecuadamente los eventos del juego, la cinemática del paciente, la visión y la señal IMU/fusión. La frecuencia de fusión es estable, alrededor de **31 Hz globales**, y la visión se mantiene alrededor de **8 Hz**.

Los puntos técnicos a revisar son:

1. **Calibración/orientación**, especialmente por la variabilidad entre cubos y rondas.
2. **Detecciones Unknown**, más frecuentes en la ronda 2.
3. **Segmentos de interacción**, que no parecen representar todavía trayectorias completas de manipulación.
4. **Picos de velocidad**, especialmente en la ronda 3, que podrían ser artefactos de tracking.

El FSR no debe considerarse un fallo cuando no se activa, ya que no es obligatorio presionarlo para manipular el cubo. En estos datos debe interpretarse solo como una señal complementaria de presión/contacto.

---

## Resumen final

El Paciente 1 realiza una ejecución funcionalmente válida del ejercicio de rehabilitación en realidad mixta. Completa las tres rondas disponibles, alcanza todos los objetivos y mantiene un rendimiento global bueno. La tarea genera movimiento relevante de la mano derecha, con aumento progresivo del espacio de trabajo y sin indicios claros de incremento proporcional de compensación con la cabeza.

Los errores registrados parecen más relacionados con selección de color, atención o interpretación de la consigna que con una imposibilidad motora. Técnicamente, el sistema ofrece datos útiles para análisis de rendimiento y cinemática, aunque conviene mejorar o revisar el registro de segmentos de interacción y la estabilidad de la calibración de orientación de los cubos.
