# Laboratorio 5 Simulación y Monitoreo de Variables Cardiovasculares y Hemodinámicas

* María Angel Benavides Silva - 5600852
* Evelyn Marcela Caro Rodríguez - 5600848

## Parte A 

Los monitores de signos vitales son equipos biomédicos diseñados para medir, procesar y mostrar en tiempo real variables fisiológicas esenciales de un paciente. Estos dispositivos permiten supervisar parámetros como la frecuencia cardíaca, la presión arterial, la saturación de oxígeno, la frecuencia respiratoria y la temperatura corporal, proporcionando información continua sobre el estado hemodinámico y respiratorio del individuo. Su utilización es fundamental en el ámbito clínico, ya que facilita la detección temprana de alteraciones fisiológicas y apoya la toma de decisiones del personal sanitario.

##
***¿Cómo colocar al uMEC 100 en modo “monitor”?***

El monitor de signos vitales uMEC 100 opera normalmente en el modo de monitorización (Monitoring Mode), el cual permite visualizar y registrar los parámetros fisiológicos del paciente en tiempo real. Para acceder a este modo, primero se debe encender el equipo y esperar a que finalice la secuencia de inicio. Posteriormente, desde el menú principal se ingresa a Operating Modes (Modos de operación) y se selecciona la opción Monitoring Mode. Una vez activado este modo, se conectan los sensores correspondientes (ECG, SpO₂, presión no invasiva, temperatura u otros parámetros disponibles) y se inicia la monitorización del paciente. El manual del equipo indica que este es el modo de funcionamiento clínico habitual, diferenciándose de otros modos disponibles como Night Mode, Privacy Mode, Demo Mode y Standby Mode.

##
***¿Qué tipo de parámetros o variables fisiológicas pueden simularse con el Pronk OxSim OX-1?***

El Pronk OxSim OX-1 es un simulador óptico diseñado para verificar el funcionamiento de sistemas de oximetría de pulso. Este equipo permite simular tres variables fisiológicas fundamentales: la saturación de oxígeno (SpO₂), la frecuencia cardíaca y el índice de perfusión. Estas simulaciones permiten comprobar la capacidad de respuesta y la exactitud de los monitores de signos vitales y oxímetros de pulso.

- **Saturación de oxígeno (SpO₂):**  representa el porcentaje de hemoglobina arterial que se encuentra transportando oxígeno. Es un indicador ampliamente utilizado para evaluar el estado de oxigenación del paciente. El OxSim OX-1 puede generar simulaciones de saturación entre distintos valores preestablecidos, incluyendo 85 %, 95 %, 98 % y 99 %, permitiendo verificar la respuesta del monitor ante diferentes condiciones clínicas.

- **Frecuencia cardíaca (Heart Rate):** corresponde al número de latidos cardíacos por minuto. Este parámetro permite comprobar si el monitor es capaz de detectar correctamente ritmos cardíacos lentos, normales o rápidos. El simulador puede generar frecuencias cardíacas de 40, 80 y 140 latidos por minuto (bpm).

- **Índice de perfusión (Perfusion Index, PI):** es una medida de la intensidad de la señal pulsátil detectada por el sensor de oximetría y está relacionada con la perfusión sanguínea periférica. El equipo puede simular condiciones de perfusión normal (PI ≈ 2.0) y de baja perfusión (PI ≈ 0.2), lo que permite evaluar el desempeño del monitor en situaciones donde la señal fisiológica es débil.

##
***¿Cuáles son las tolerancias o errores máximos permitidos (EMP) para cada parámetro fisiológico?***

Los errores máximos permitidos (EMP) corresponden a las desviaciones aceptables entre el valor simulado y el valor medido por el monitor. En el caso del Pronk OxSim OX-1, la variable para la cual se especifican tolerancias directamente es la saturación de oxígeno (SpO₂). El manual indica que las simulaciones están diseñadas para producir valores dentro de la tolerancia propia de los sensores de oximetría utilizados. Los sensores reutilizables presentan normalmente una tolerancia de ±2 %, mientras que algunos sensores desechables poseen una tolerancia de ±3 %. Además, muchos oxímetros incorporan una incertidumbre adicional aproximada de ±1 %, por lo que el error global observado puede incrementarse dependiendo de la combinación de sensor y monitor empleada.

Para la frecuencia cardíaca, el OxSim genera señales de 40, 80 y 140 bpm con el objetivo de verificar la capacidad de respuesta de los monitores. Aunque el manual del simulador no especifica un error máximo permitido para este parámetro, los monitores de signos vitales suelen aceptar errores cercanos a ±1 bpm en condiciones normales de operación, valor utilizado habitualmente en procedimientos de verificación metrológica clínica.

Respecto al índice de perfusión (PI), el simulador ofrece condiciones de perfusión normal (PI ≈ 2,0) y baja perfusión (PI ≈ 0,2). Sin embargo, la documentación revisada no establece un error máximo permitido universal para este parámetro, ya que su función principal es evaluar la calidad de la señal detectada por el oxímetro más que realizar una medición clínica independiente.

## Parte B 

***Video Prueba 1 (40 BOM / 85 %):***

##
***Video Prueba  (40 BOM / 85 %):***

##
***Video Prueba  (40 BOM / 85 %):***

##
***Video Prueba  (40 BOM / 85 %):***

##
***Tabla de verificación de alarmas:***

| Prueba | Modo del OxSim | Límite configurado (alto/bajo) | Valor simulado | ¿Alarma activa? (sí/no) | Tiempo de estabilización | Tiempo de respuesta de la alarma | Tiempo total (desde que se conecta el simulador, hasta que enciende la alarma) |
|---|---|---|---|---|---|---|---|
| 1 | 95 % 40 bpm | Bajo SpO₂: 90 %<br>Alto SpO₂: 97 % | FC = 40 bpm<br>SpO₂ = 95 % | Sí | 1:03 min | 7 s | 1:10 min |
| 2 | 85 % 80 bpm | Bajo SpO₂: 90 %<br>Alto SpO₂: 97 % | FC = 80 bpm<br>SpO₂ = 85 % | Sí | 1:24 min | 7 s | 1:31 min |
| 3 | 99 % Low Perf | Bajo SpO₂: 90 %<br>Alto SpO₂: 97 % | "Low Perfusion"<br>SpO₂ = 99 % | Sí | 17 s | 10 s | 27 s |
| 4 | 98 % 140 bpm | Bajo SpO₂: 90 %<br>Alto SpO₂: 97 % | FC = 140 bpm<br>SpO₂ = 98 % | Sí | 16 s | 4 s | 20 s |

## Preguntas 

***Pregunta 1: ¿Cuál es el principio de operación del Pronk OxSim OX-1 para simular una onda pulsátil?***

El Pronk OxSim OX-1 funciona mediante un principio de simulación óptica, reproduciendo las señales luminosas que normalmente atravesarían un tejido biológico durante la medición de la oximetría de pulso. El dispositivo genera variaciones controladas en la absorción de luz roja e infrarroja, imitando los cambios producidos por el flujo sanguíneo arterial durante cada latido cardíaco. De esta manera, el monitor interpreta la señal generada por el simulador como si proviniera de un paciente real, permitiendo verificar la medición de saturación de oxígeno (SpO₂), frecuencia cardíaca e índice de perfusión.

***Pregunta 2: ¿Por qué la SpO2 baja puede ser un falso positivo (falsa alarma) en una situación de mala perfusión?***

La medición de la SpO₂ depende de la detección de una señal pulsátil adecuada en los tejidos periféricos. Cuando existe mala perfusión periférica, el flujo sanguíneo arterial disminuye y la señal pulsátil captada por el sensor se vuelve débil. En estas condiciones, el oxímetro puede tener dificultades para diferenciar la señal arterial del ruido generado por movimientos, interferencias eléctricas o baja amplitud de la señal. Como consecuencia, el monitor puede mostrar valores de saturación artificialmente bajos, aunque la oxigenación real del paciente sea normal, generando una falsa alarma o un falso positivo de hipoxemia. Por esta razón, la baja perfusión constituye una de las principales fuentes de error en la oximetría de pulso.
  

## Conclusiones 



## Bibliografías 
[1] Mindray Bio-Medical Electronics Co., Ltd., uMEC10/uMEC12/uMEC15 Patient Monitor Operator's Manual, Shenzhen, China, 2016. Disponible en ManualsLib.

[2] Pronk Technologies, OX-1 OxSim® Optical SpO₂ Pulse Oximeter Simulator - Product Specifications, Pronk Technologies Inc.

[3] Pronk Technologies, OX-1 OxSim Optical SpO₂ Simulator Specifications, MedWrench Equipment Database.

[4] Mindray, Monitor de pacientes uMEC, especificaciones y descripción del producto, Mindray Medical International.
