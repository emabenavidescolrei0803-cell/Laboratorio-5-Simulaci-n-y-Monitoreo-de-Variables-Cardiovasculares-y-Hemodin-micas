# Laboratorio 5 Simulación y Monitoreo de Variables Cardiovasculares y Hemodinámicas

* María Angel Benavides Silva - 5600852
* Evelyn Marcela Caro Rodríguez - 5600848

## Parte A 

Los monitores de signos vitales son equipos biomédicos diseñados para medir, procesar y mostrar en tiempo real variables fisiológicas esenciales de un paciente. Estos dispositivos permiten supervisar parámetros como la frecuencia cardíaca, la presión arterial, la saturación de oxígeno, la frecuencia respiratoria y la temperatura corporal, proporcionando información continua sobre el estado hemodinámico y respiratorio del individuo. Su utilización es fundamental en el ámbito clínico, ya que facilita la detección temprana de alteraciones fisiológicas y apoya la toma de decisiones del personal sanitario[1]. 

##
***¿Cómo colocar al uMEC 100 en modo “monitor”?***

El monitor de signos vitales uMEC 100 opera normalmente en el modo de monitorización (Monitoring Mode), el cual permite visualizar y registrar los parámetros fisiológicos del paciente en tiempo real. Para acceder a este modo, primero se debe encender el equipo y esperar a que finalice la secuencia de inicio. Posteriormente, desde el menú principal se ingresa a Operating Modes (Modos de operación) y se selecciona la opción Monitoring Mode. Una vez activado este modo, se conectan los sensores correspondientes (ECG, SpO₂, presión no invasiva, temperatura u otros parámetros disponibles) y se inicia la monitorización del paciente. El manual del equipo indica que este es el modo de funcionamiento clínico habitual, diferenciándose de otros modos disponibles como Night Mode, Privacy Mode, Demo Mode y Standby Mode[1][4].

##
***¿Qué tipo de parámetros o variables fisiológicas pueden simularse con el Pronk OxSim OX-1?***

El Pronk OxSim OX-1 es un simulador óptico diseñado para verificar el funcionamiento de sistemas de oximetría de pulso. Este equipo permite simular tres variables fisiológicas fundamentales: la saturación de oxígeno (SpO₂), la frecuencia cardíaca y el índice de perfusión. Estas simulaciones permiten comprobar la capacidad de respuesta y la exactitud de los monitores de signos vitales y oxímetros de pulso[2][3].

- **Saturación de oxígeno (SpO₂):**  representa el porcentaje de hemoglobina arterial que se encuentra transportando oxígeno. Es un indicador ampliamente utilizado para evaluar el estado de oxigenación del paciente. El OxSim OX-1 puede generar simulaciones de saturación entre distintos valores preestablecidos, incluyendo 85 %, 95 %, 98 % y 99 %, permitiendo verificar la respuesta del monitor ante diferentes condiciones clínicas[4].

- **Frecuencia cardíaca (Heart Rate):** corresponde al número de latidos cardíacos por minuto. Este parámetro permite comprobar si el monitor es capaz de detectar correctamente ritmos cardíacos lentos, normales o rápidos. El simulador puede generar frecuencias cardíacas de 40, 80 y 140 latidos por minuto (bpm).[4].

- **Índice de perfusión (Perfusion Index, PI):** es una medida de la intensidad de la señal pulsátil detectada por el sensor de oximetría y está relacionada con la perfusión sanguínea periférica. El equipo puede simular condiciones de perfusión normal (PI ≈ 2.0) y de baja perfusión (PI ≈ 0.2), lo que permite evaluar el desempeño del monitor en situaciones donde la señal fisiológica es débil[4]. 

##
***¿Cuáles son las tolerancias o errores máximos permitidos (EMP) para cada parámetro fisiológico?***

Los errores máximos permitidos (EMP) corresponden a las desviaciones aceptables entre el valor simulado y el valor medido por el monitor. En el caso del Pronk OxSim OX-1, la variable para la cual se especifican tolerancias directamente es la saturación de oxígeno (SpO₂). El manual indica que las simulaciones están diseñadas para producir valores dentro de la tolerancia propia de los sensores de oximetría utilizados. Los sensores reutilizables presentan normalmente una tolerancia de ±2 %, mientras que algunos sensores desechables poseen una tolerancia de ±3 %. Además, muchos oxímetros incorporan una incertidumbre adicional aproximada de ±1 %, por lo que el error global observado puede incrementarse dependiendo de la combinación de sensor y monitor empleada.

Para la frecuencia cardíaca, el OxSim genera señales de 40, 80 y 140 bpm con el objetivo de verificar la capacidad de respuesta de los monitores. Aunque el manual del simulador no especifica un error máximo permitido para este parámetro, los monitores de signos vitales suelen aceptar errores cercanos a ±1 bpm en condiciones normales de operación, valor utilizado habitualmente en procedimientos de verificación metrológica clínica.

Respecto al índice de perfusión (PI), el simulador ofrece condiciones de perfusión normal (PI ≈ 2,0) y baja perfusión (PI ≈ 0,2). Sin embargo, la documentación revisada no establece un error máximo permitido universal para este parámetro, ya que su función principal es evaluar la calidad de la señal detectada por el oxímetro más que realizar una medición clínica independiente[1].

## Parte B 

## Videos

***Video Prueba 1 (40 BPM / 95 %):***

[Prueba 1.zip](https://github.com/user-attachments/files/34406157/Prueba.1.zip)

***Video Prueba 2 (80 BPM / 85 %):***

[Prueba 2.zip](https://github.com/user-attachments/files/34406323/Prueba.2.zip)

***Video Prueba 3 (Low Perfusion / 99 %):***

[Prueba 3.zip](https://github.com/user-attachments/files/34406324/Prueba.3.zip)

***Video Prueba 4 (140 BPM / 98 %):***

[Prueba 4.zip](https://github.com/user-attachments/files/34406322/Prueba.4.zip)

## ***Tabla de verificación de alarmas:***

| Prueba | Modo del OxSim | Límite configurado (alto/bajo) | Valor simulado | ¿Alarma activa? (sí/no) | Tiempo de estabilización | Tiempo de respuesta de la alarma | Tiempo total (desde que se conecta el simulador, hasta que enciende la alarma) |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| 1 | 95 % 40 bpm | Bajo SpO₂: 90 %<br>Alto SpO₂: 97 % | FC=40bpm <br>SpO₂ = 95 % | Sí | 1:03 min | 7 s | 1:10 min |
| 2 | 85 % 80 bpm | Bajo SpO₂: 90 %<br>Alto SpO₂: 97 % | FC=80bpm <br>SpO₂ = 85 % | Sí | 1:24 min | 7 s | 1:31 min |
| 3 | 99 % Low Perf | Bajo SpO₂: 90 %<br>Alto SpO₂: 97 % | "Low Perfusion" <br>SpO₂ = 99 % | Sí | 17 s | 10 s | 27 s |
| 4 | 98 % 140 bpm | Bajo SpO₂: 90 %<br>Alto SpO₂: 97 % | FC=140bpm <br>SpO₂ = 98 % | Sí | 16 s | 4 s | 20 s |

- Prueba 1 (FC = 40 bpm): Se activó la alarma debido a que la frecuencia cardíaca descendió severamente por debajo de los límites fisiológicos normales (bradicardia severa), a pesar de que la SpO_2(95%) estaba dentro de los límites configurados (90% - 97%).
- Prueba 2 (SpO_2 = 85%): La alarma se disparó correctamente al violar el límite inferior de saturación (90%), simulando una condición de hipoxia.
- Prueba 3 (SpO}_2 = 99%, Low Perf): Activó la alarma al superarse el límite superior configurado (97%). En este modo de baja perfusión, la baja amplitud de la onda fotopletismográfica exige al monitor aumentar el nivel de ganancia/filtrado, tardando un poco más en calcular la alarma de respuesta.
- Prueba 4 (FC = 140 bpm, SpO_2 = 98%): Activó la alarma sonora y visual debido tanto a la taquicardia (140 bpm) como al sobrepaso del límite superior de SpO_2 (97%).


Tiempo de Respuesta del Monitor: osciló entre 4 s y 10 s desde el momento en que el monitor procesó la condición de alarma. Esto cumple de manera óptima con los estándares internacionales de seguridad médica (IEC 60601-1-8), garantizando una alerta rápida ante eventos críticos.

Tiempo de Estabilización: se observó una diferencia notable entre las pruebas 1-2 ( 1 min 03 s - 1 min 24 s) y las pruebas 3-4 ( 16 s - 17 s). Esto se debe a la latencia en el procesamiento digital de señales (DSP) del monitor (algoritmos de promediado de pulsos para filtrar ruido y artefactos de movimiento) y al tiempo que requiere el simulador OxSim para estabilizar la salida de señal tras cambiar la configuración del parámetro.


## ***Tabla de errores:***

Error absoluto = |valor uMEC 100 − valor simulado|

Error porcentual = (error absoluto / valor simulado) × 100

| Prueba | Variable | Valor simulado (OxSim) | Valor mostrado (uMEC 100) | Error absoluto | Error porcentual (%) |
|:---:|:---:|:---:|:---:|:---:|:---:|
| 1 | FC (bpm) | 40 | 40 |0 | 0 %|
| 1 | SpO₂ (%) | 95 | 96| 1|1.05263 %|
| 2 | FC (bpm) | 80 |80 | 0| 0 % |
| 2 | SpO₂ (%) | 85 | 85|0 | 0 %|
| 3 | FC (bpm) | | 80| | |
| 3 | SpO₂ (%) | 99 | 100|1 | 1.01010|
| 4 | FC (bpm) | 140 | 140|0 |0 % |
| 4 | SpO₂ (%) | 98 | 99|1 | 1.02041 %|

Frecuencia Cardíaca (FC):
En todas las condiciones probadas (40, 80 y 140 bpm), el monitor mostró exactamente el valor simulado por el OxSim. Esto resultó en un error absoluto de 0 bpm y un error porcentual del 0 %, demostrando una alta precisión en la detección y conteo de la frecuencia de pulso a través del sensor de fotopletismografía (PPG).  

Saturación Periférica de Oxígeno (SpO_2):
Se observó una desviación estándar constante de +1% respecto a la señal simulada en la mayoría de los casos (95 -> 96 %, 99 -> 100% y 98 -> 99%).   Los errores porcentuales obtenidos (1.01 % a 1.05 %) se mantienen dentro de los rangos normativos de tolerancia clínica estándar para pulsioxímetros, que usualmente aceptan un Error Máximo Permitido (EMP) de ± 2 % a ± 3 % en el rango de 70 % a 100 %.   En la prueba 2 (SpO_2 = 85 %), el valor mostrado fue exactamente de 85 % (0 % de error), lo que confirma un comportamiento lineal y confiable del algoritmo de cálculo del equipo uMEC 100.

## Preguntas 

***Pregunta 1: ¿Cuál es el principio de operación del Pronk OxSim OX-1 para simular una onda pulsátil?***

El Pronk OxSim OX-1 funciona mediante un principio de simulación óptica basado en la misma tecnología empleada por los oxímetros de pulso clínicos. Su funcionamiento se fundamenta en la ley de Beer-Lambert, la cual establece que la cantidad de luz absorbida por un material depende de las propiedades del medio atravesado y de la concentración de las sustancias presentes. En la oximetría de pulso, esta ley se aplica para analizar la absorción de dos longitudes de onda específicas: luz roja, alrededor de 660 nm, y luz infrarroja, alrededor de 940 nm. La hemoglobina oxigenada y la hemoglobina desoxigenada absorben estas longitudes de onda en proporciones diferentes, lo que permite determinar el nivel de saturación de oxígeno en la sangre.

Para reproducir este fenómeno sin utilizar un paciente real, el OxSim genera señales luminosas controladas que imitan el comportamiento óptico de la sangre arterial durante el ciclo cardíaco. El simulador modifica periódicamente la intensidad de la luz roja e infrarroja para recrear las variaciones de absorción que normalmente ocurren cuando aumenta y disminuye el volumen de sangre en los vasos sanguíneos con cada latido. De esta forma, el sensor del oxímetro detecta una señal pulsátil artificial equivalente a la que recibiría al colocarse sobre un dedo humano. A partir de esta señal, el monitor calcula la saturación de oxígeno (SpO₂), la frecuencia cardíaca y el índice de perfusión utilizando los mismos algoritmos que emplearía durante la monitorización de un paciente. Este principio de operación permite verificar el desempeño y la exactitud de los sistemas de oximetría de pulso bajo condiciones controladas y repetibles. OxSim SpO2 Simulator Operator’s Manual y OX-1 OxSim Optical SpO2 Pulse Oximeter Simulator.

***Pregunta 2: ¿Por qué la SpO2 baja puede ser un falso positivo (falsa alarma) en una situación de mala perfusión?***

La medición de la SpO₂ depende de la detección de una señal pulsátil adecuada en los tejidos periféricos. Cuando existe mala perfusión periférica, el flujo sanguíneo arterial disminuye y la señal pulsátil captada por el sensor se vuelve débil. En estas condiciones, el oxímetro puede tener dificultades para diferenciar la señal arterial del ruido generado por movimientos, interferencias eléctricas o baja amplitud de la señal. Como consecuencia, el monitor puede mostrar valores de saturación artificialmente bajos, aunque la oxigenación real del paciente sea normal, generando una falsa alarma o un falso positivo de hipoxemia. Por esta razón, la baja perfusión constituye una de las principales fuentes de error en la oximetría de pulso.
  

## Conclusiones 

En esta práctica evaluamos qué tan preciso y confiable es el monitor de signos vitales cuando se enfrenta a diferentes situaciones clínicas, usando el simulador OxSim OX-1 para recrear señales fisiológicas reales. Los resultados mostraron que el equipo es bastante exacto: midió la frecuencia cardíaca sin margen de error (0 %) y los valores de saturación de oxígeno (SpO₂) se mantuvieron muy cerca de lo simulado, con diferencias de apenas el 1.05 %, manteniéndose dentro de los límites de tolerancia aceptables. Además, el sistema de alarmas respondió a tiempo (tomando entre 4 y 10 segundos en activarse) ante eventos de bradicardia, taquicardia e hipoxia, lo que demuestra que cumple bien con las exigencias de seguridad para uso clínico (como la norma IEC 60601-1-8). Hacer este tipo de pruebas nos permite comprobar que la tecnología biomédica está funcionando correctamente para brindar una atención segura al paciente. Como trabajo a futuro, valdría la pena probar el monitor con un número mayor de puntos de medición y bajo situaciones de movimiento o interferencias, para ver qué tan bien filtran la señal sus algoritmos en entornos más complejos.

## Bibliografías 
[1] Mindray Bio-Medical Electronics Co., Ltd., uMEC10/uMEC12/uMEC15 Patient Monitor Operator's Manual, Shenzhen, China, 2016. Disponible en ManualsLib.

[2] Pronk Technologies, OX-1 OxSim® Optical SpO₂ Pulse Oximeter Simulator - Product Specifications, Pronk Technologies Inc.

[3] Pronk Technologies, OX-1 OxSim Optical SpO₂ Simulator Specifications, MedWrench Equipment Database.

[4] Mindray, Monitor de pacientes uMEC, especificaciones y descripción del producto, Mindray Medical International.
