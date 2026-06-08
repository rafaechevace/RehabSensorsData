# Informe del ejercicio de rehabilitación en realidad mixta — Persona 2

## 1. Alcance del análisis

Se ha analizado el archivo comprimido `SESSION_20260518_123146_R2_RH.zip`. Dentro del ZIP aparecen tres carpetas de sesión:

- `SESSION_20260518_123118_R1_RH`
- `SESSION_20260518_123146_R2_RH`
- `SESSION_20260518_123232_R4_RH`

Por tanto, los datos contienen registros completos de las rondas 1 y 2, y una sesión correspondiente a la ronda 4. No aparece una carpeta con los archivos de la ronda 3. Sin embargo, los contadores acumulados al inicio de la ronda 4 indican que la ronda 3 existió y que se completó antes de comenzar la ronda 4.

La configuración registrada del ejercicio es:

`hand=Right rounds=5 targets=10`

El ejercicio se realiza con la mano derecha.

---

## 2. Resumen ejecutivo

La Persona 2 muestra un rendimiento funcional muy alto en las rondas completadas disponibles. Las rondas 1 y 2 se completan con 20 aciertos, 1 único error de color y ningún timeout. Además, los contadores acumulados al inicio de la ronda 4 permiten inferir que la ronda 3 también fue completada, alcanzando 30 aciertos acumulados y 2 fallos acumulados antes de iniciar la ronda 4.

La ronda 4 no debe considerarse comparable con las anteriores porque aparece incompleta y contiene una interrupción temporal muy grande de aproximadamente 240,07 s entre eventos. En esa ronda se registran 7 aciertos y 3 timeouts, pero no aparece evento `RoundComplete`.

En conjunto, el paciente/persona presenta buena capacidad para completar los objetivos, buen ritmo de ejecución y una secuencia de aciertos muy consistente, especialmente en la primera parte del ejercicio. La principal incidencia del registro es la discontinuidad de la ronda 4 y la ausencia de los archivos específicos de la ronda 3.

---

## 3. Resultados funcionales por ronda disponible

| Ronda | Estado | Duración registrada | Aciertos | Errores de color | Timeouts | Precisión con timeout | Puntuación final/acumulada | Mejor combo |
|---:|---|---:|---:|---:|---:|---:|---:|---:|
| 1 | Completa | 24,39 s | 10 | 0 | 0 | 100,00 % | 3250 | 10 |
| 2 | Completa | 20,89 s | 10 | 1 | 0 | 90,91 % | 6525 | 11 |
| 3 | No incluida como carpeta | — | 10 inferidos | 1 fallo acumulado inferido | — | — | 9750 al inicio de R4 | 11 al inicio de R4 |
| 4 | Incompleta | 281,50 s | 7 | 0 | 3 | 70,00 % | 14125 | 16 |

### Interpretación

- Las rondas 1 y 2 son válidas y comparables.
- La ronda 3 no puede analizarse técnicamente porque faltan sus archivos, pero los acumulados del juego indican que se completó.
- La ronda 4 queda incompleta y contiene una pausa/interrupción larga; por tanto, no debe mezclarse con las rondas completas para calcular rendimiento motor comparable.

---

## 4. Rendimiento global

### 4.1. Rondas completas con archivos disponibles: R1 + R2

| Métrica | Valor |
|---|---:|
| Rondas completas analizadas con archivos | 2 |
| Objetivos completados | 20 |
| Aciertos | 20 |
| Errores de color | 1 |
| Timeouts | 0 |
| Precisión | 95,24 % |
| Tiempo total efectivo | 45,28 s |
| Ritmo medio | 26,50 aciertos/min |

Estas dos rondas reflejan un rendimiento muy alto: ejecución rápida, pocos errores y ningún timeout.

### 4.2. Rendimiento acumulado inferido hasta el inicio de R4

Al comenzar la ronda 4, el juego registra:

| Métrica acumulada al inicio de R4 | Valor |
|---|---:|
| Aciertos acumulados | 30 |
| Fallos acumulados | 2 |
| Puntuación acumulada | 9750 |
| Combo actual | 10 |
| Mejor combo | 11 |

Esto permite inferir que la ronda 3 se completó con 10 aciertos adicionales y 1 fallo adicional respecto a la ronda 2.

### 4.3. Estado final del registro disponible

Al final de la sesión incompleta de ronda 4:

| Métrica acumulada final | Valor |
|---|---:|
| Aciertos acumulados | 37 |
| Fallos acumulados | 5 |
| Puntuación final registrada | 14125 |
| Mejor combo alcanzado | 16 |

Si se considera todo lo registrado, incluyendo la ronda 4 incompleta, la precisión acumulada sería aproximadamente 88,10 %. No obstante, este valor debe interpretarse con cautela porque la ronda 4 no es una ejecución continua ni completa.

---

## 5. Análisis de errores y eventos relevantes

### Ronda 1

La ronda 1 no contiene errores ni timeouts. Se completan los 10 objetivos con una secuencia limpia. El combo final alcanza 10.

### Ronda 2

La ronda 2 contiene un único error de color:

| Tiempo | Esperado | Colocado |
|---:|---|---|
| 4,2094 s | Red | Blue |

Después del error, la persona recupera la secuencia y completa los 10 objetivos de la ronda.

### Ronda 4 incompleta

La ronda 4 contiene 7 aciertos y 3 timeouts:

| Tiempo | Evento | Color esperado | Detalles |
|---:|---|---|---|
| 29,2763 s | Timeout | Blue | limit=14s |
| 269,3437 s | Timeout | Red | limit=14s |
| 283,5773 s | Timeout | Blue | limit=13s |

Entre el primer timeout y el segundo timeout hay una interrupción de aproximadamente 240,07 s. Esta pausa altera completamente la comparabilidad de la ronda 4 respecto a las rondas 1 y 2.

---

## 6. Cinemática de la mano derecha

| Métrica | Ronda 1 | Ronda 2 | Ronda 4 incompleta |
|---|---:|---:|---:|
| Trayectoria mano derecha | 11,22 m | 15,89 m | 21,70 m |
| Velocidad media mano derecha | 0,41 m/s | 0,69 m/s | 0,08 m/s |
| Percentil 95 velocidad | 1,47 m/s | 2,74 m/s | 1,40 m/s |
| Trayectoria cabeza | 2,22 m | 3,06 m | 4,67 m |
| Relación cabeza/mano | 19,82 % | 19,28 % | 21,51 % |

### Interpretación cinemática

En las dos rondas completas, la trayectoria de la mano derecha aumenta de 11,22 m a 15,89 m, mientras que la duración de la ronda disminuye de 24,39 s a 20,89 s. Esto indica una ejecución más rápida y con mayor desplazamiento acumulado en la segunda ronda.

La relación cabeza/mano se mantiene muy parecida entre las rondas 1 y 2, alrededor del 19 %. Esto sugiere que el aumento de movimiento de la mano en la segunda ronda no viene acompañado de un aumento proporcional de movimiento de cabeza. No hay evidencia clara, con estos datos, de una compensación creciente mediante cabeza/tronco en las dos rondas válidas.

La ronda 4 no debe usarse para comparar velocidad media ni frecuencia de movimiento, porque incluye una pausa temporal muy grande y además presenta valores de tracking extremos, como rangos verticales anómalos. Sí puede considerarse útil como evidencia de que la sesión fue interrumpida o perdió continuidad.

---

## 7. Rango espacial de la mano derecha

| Ronda | Rango X | Rango Y | Rango Z |
|---:|---:|---:|---:|
| 1 | 0,62 m | 0,20 m | 0,54 m |
| 2 | 0,65 m | 0,25 m | 0,61 m |
| 4 incompleta | 0,60 m | 1,50 m | 0,96 m |

Entre las rondas 1 y 2 se observa un rango espacial amplio y consistente, especialmente en X y Z. La ronda 2 presenta mayor profundidad de movimiento en Z, lo que puede reflejar trayectorias más extensas o un mayor uso del espacio de trabajo.

El rango Y de la ronda 4 es anómalo y no debe interpretarse clínicamente sin revisar la interrupción y la posible pérdida de seguimiento.

---

## 8. Calidad de visión

| Métrica | Ronda 1 | Ronda 2 | Ronda 4 incompleta |
|---|---:|---:|---:|
| Detecciones totales | 243 | 200 | 218 |
| Frecuencia visual aproximada | 9,06 Hz | 8,78 Hz | 0,77 Hz |
| Detecciones Unknown | 10 | 18 | 16 |
| Confianza media | 0,699 | 0,684 | 0,677 |

### Distribución por clase visual

| Ronda | Red | Blue | Unknown |
|---:|---:|---:|---:|
| 1 | 117 | 116 | 10 |
| 2 | 96 | 86 | 18 |
| 4 incompleta | 80 | 122 | 16 |

En las rondas 1 y 2 la frecuencia visual se mantiene en torno a 9 Hz y 8,8 Hz, respectivamente. La ronda 4 muestra una frecuencia aparente muy baja porque el cálculo incluye la gran pausa temporal; por tanto, no es comparable.

En todas las detecciones registradas, los cuatro keypoints aparecen visibles, lo que indica que cuando el cubo se detecta, la información geométrica asociada a los puntos clave está completa.

---

## 9. IMU, fusión y estado de cubos

| Métrica | Ronda 1 | Ronda 2 | Ronda 4 incompleta |
|---|---:|---:|---:|
| Muestras `cube_state` | 842 | 708 | 1840 |
| Frecuencia total aproximada | 30,86 Hz | 30,90 Hz | 6,48 Hz |
| Frecuencia por cubo | 15,43 Hz | 15,45 Hz | 3,24 Hz |

En las rondas 1 y 2, la frecuencia de fusión/estado de cubos es muy estable, alrededor de 31 Hz globales y 15,5 Hz por cubo. Esto indica buena continuidad del registro técnico durante las rondas completas.

La ronda 4 muestra una frecuencia aparente más baja porque incluye la pausa larga. No debe compararse directamente con las rondas 1 y 2.

### Señal FSR / agarre

| Ronda | `is_gripping` CubeRed | `is_gripping` CubeBlue | Máx. raw CubeRed | Máx. raw CubeBlue |
|---:|---:|---:|---:|---:|
| 1 | 10 | 13 | 2303 | 58 |
| 2 | 6 | 5 | 40 | 56 |
| 4 incompleta | 5 | 1 | 40 | 15 |

La señal FSR se interpreta como complementaria. No debe utilizarse como criterio obligatorio de agarre, porque la persona puede coger y manipular el cubo sin presionar la zona instrumentada. En esta persona, la ronda 1 sí presenta valores elevados en el cubo rojo, probablemente por un contacto directo con el sensor en algunos momentos.

---

## 10. Segmentos de interacción

| Ronda | Segmentos registrados | Duración total de segmentos | Longitud total de segmentos |
|---:|---:|---:|---:|
| 1 | 23 | 0,83 s | 0,00 m |
| 2 | 11 | 0,28 s | 0,00 m |
| 4 incompleta | 6 | 0,02 s | 0,00 m |

Aunque hay segmentos registrados, la longitud total aparece como 0 m y las duraciones acumuladas son muy pequeñas. Por tanto, `interaction_segments` no debe usarse todavía como fuente principal para analizar ciclos completos de manipulación. Es más fiable utilizar `game_events` para rendimiento y `patient_kinematics` para movimiento.

---

## 11. Calibración

| Ronda | Cubo | Error absoluto medio | Error simétrico medio | Nº muestras |
|---:|---|---:|---:|---:|
| 1 | CubeRed | 14,73° | 14,73° | 9 |
| 1 | CubeBlue | 61,10° | 28,90° | 7 |
| 2 | CubeRed | 9,74° | 9,74° | 4 |
| 2 | CubeBlue | 75,34° | 14,66° | 3 |
| 4 | CubeRed | — | — | 0 |
| 4 | CubeBlue | 95,56° | 5,56° | 3 |

### Interpretación de calibración

En las rondas 1 y 2, el cubo rojo presenta errores absolutos medios relativamente bajos, mientras que el cubo azul muestra errores absolutos altos pero errores simétricos mucho menores. Esto sugiere una ambigüedad de orientación asociada a la simetría del cubo azul.

En la ronda 4 solo aparecen registros de calibración para CubeBlue. El error absoluto es muy alto, pero el error simétrico es bajo. Esto refuerza la idea de que la orientación absoluta puede estar afectada por simetrías o por una equivalencia geométrica del cubo, aunque funcionalmente el sistema sigue permitiendo avanzar en el juego.

---

## 12. Conclusiones

### Conclusión funcional

La Persona 2 presenta un rendimiento funcional muy bueno en las rondas completas disponibles. Completa las rondas 1 y 2 con 20 aciertos, un único error y ningún timeout. Además, los contadores acumulados indican que la ronda 3 también fue completada, aunque sus archivos no están incluidos en el ZIP.

La ejecución válida y comparable del ejercicio debe centrarse principalmente en las rondas 1 y 2, y opcionalmente en los acumulados inferidos hasta el inicio de la ronda 4.

### Conclusión sobre precisión y ritmo

La ronda 1 es perfecta en términos de aciertos y errores: 10 aciertos de 10. La ronda 2 mantiene un rendimiento muy alto, con 10 aciertos y un único error de color. El ritmo es muy elevado: las dos rondas completas disponibles suman 20 aciertos en 45,28 s, equivalente a unos 26,50 aciertos/min.

### Conclusión cinemática

La mano derecha muestra una trayectoria amplia y activa. En la ronda 2 aumenta la distancia recorrida respecto a la ronda 1 y también la velocidad media, lo que sugiere una ejecución más dinámica. La relación entre movimiento de cabeza y movimiento de mano se mantiene estable, alrededor del 19 %, sin indicios claros de incremento de compensación cefálica en las dos rondas válidas.

### Conclusión técnica

El sistema registra adecuadamente eventos, cinemática, visión y fusión/IMU durante las rondas completas. La frecuencia de fusión es estable en torno a 31 Hz globales y la visión se mantiene cerca de 9 Hz. La principal limitación técnica del ZIP es la ausencia de la carpeta de la ronda 3 y la interrupción de la ronda 4, que impide tratarla como ronda continua.

### Conclusión sobre la ronda 4

La ronda 4 debe marcarse como incompleta o no comparable. Contiene 7 aciertos y 3 timeouts, pero presenta una interrupción de aproximadamente 240,07 s y no incluye evento de finalización de ronda. Por tanto, no debería utilizarse para comparar rendimiento motor con las rondas 1 y 2.

---

## 13. Resumen final

La Persona 2 realiza una ejecución muy sólida del ejercicio en las rondas válidas disponibles. El rendimiento funcional es alto, la precisión es elevada y el ritmo de ejecución es rápido. La persona completa al menos tres rondas según los acumulados del juego, aunque solo dos están disponibles con archivos completos para análisis técnico detallado.

Para análisis científico o clínico, se recomienda usar como base principal las rondas 1 y 2. La ronda 3 puede mencionarse solo a partir de los contadores acumulados, y la ronda 4 debe excluirse de comparativas cuantitativas por estar incompleta y contener una interrupción temporal marcada.
