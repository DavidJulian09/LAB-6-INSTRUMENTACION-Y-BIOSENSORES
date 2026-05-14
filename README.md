# LAB 6: SIMULACIÓN Y MONITOREO DE VARIABLES CARDIOVASCULARES Y HEMODINÁMICAS

## I. INTRODUCCIÓN

En un entorno clínico, es fundamental contar con equipos capaces de monitorear variables fisiológicas específicas, tales como la frecuencia cardíaca (HR) y la saturación periférica de oxígeno (SpO2) de forma continua; y no solo se limita en el monitoreo, sino que se requiere de equipos capaces de generar alarmas cuando las señales fisiológicas de los pacientes salen de los parámetros estables y que, en consecuencia, simbolizan un riesgo inmediato al paciente. Por lo anterior, se requieren de equipos especializados en simular patologías particulares, como arritmias e hipóxia, con el objetivo de que estos equipos pongan a prueba la capcidad diagnostica y de alerta de otros como lo es el monitor de signos vitales. [1]

Justamente el caso anterior es el que se pondrá a prueba en el presente laboratorio, haciendo uso de un simulador Pronk OxSim, distribuidos por Medical IT y compatible con pulsoxímetros, se evaluará la funcionalidad y presición de un monitor de signos vitales BeneHeart D30 (MINDRAY) presente en el laboratorio, todo mediante el desarrollo de los siguientes objetivos: [1]

### Objetivo general:

Operar con el simulador Pronk OxSim (OX-1) y el monitor de signos vitales BeneHeart D30 para pruebas funcionales.

### Objetivos específicos:

• Identificar los modos de operación de un simulador de parámetros hemodinámicos (Pronk OxSim).

• Verificar los límites de medición de un monitor de signos vitales mediante simulación de variables hemodinámicas.

• Interpretar variaciones en los parámetros hemodinámicos asociadas a estados fisiológicos y patológicos.


## II. MARCO TEÓRICO

### A) Modo "monitor" en el BeneHeart D30

El BeneHeart D30 es un equipo múltiple funciones que integra monitorización de signos vitales, desfibrilación, marcapasos externo, alertas, entre otros; el modo "monitor" es el estado operativo en el que el equipo actúa exclusivamente como monitor de parámetros fisiológicos (ECG, SpO₂, NIBP, CO₂, respiración...), es decir, es el modo estándar para la vigilancia continua del paciente. Como otras caracteísticas de este modo, es la presencia de alarmas fisiológicas y técnicas completamente configurables en cada parámetro. Ahora bien, el procedimiento paso a paso para entrar en modo “Monitor” es el siguiente: [2]




### B) Parámetros y variables fisiológicas simulables en el Pronk OxSim OX-1

El Pronk OxSim OX-1 (Medical IT) es un simulador de parámetros hemodinámicos diseñado específicamente para probar monitores de signos vitales, especialmente la pulsioximetría (SpO₂) y la frecuencia cardíaca (HR), sin embargo, el dispositivo no permite un rango continuo de valores, sino que opera en modos predefinidos de saturación de oxígeno y frecuencia de pulso. Ahora bien, los parámetros simulables son: [3]

#### 1. Saturación de oxígeno (SpO₂):

Como se dijo solo posee ciertos valores pre-establecidos, con el objetivo de simular diferentes niveles de oxigenación sanguínea lo cuales son 85% representa hipoxemia moderada; 95% y 98% son normales; 99% se usa en baja perfusión.

#### 2. Frecuencia cardiaca / de pulso (HR / PR):

Simula la frecuencia de pulso periférico que el monitor detecta a partir de la señal fotopletismográfica (PPG), posee valores preestablecidos de 40 bpm (simula bradicardia); 80 bpm (frecuencia normal); 140 bpm (simula taquicardia).

#### 3. Índice de perfusión (PI):

El OxSim fija un índice de perfusión (intensidad del pulso sanguíneo) en un valor típico de 2.0, que corresponde a una señal de calidad media, este es un valor que no se puede variar.

#### 4. Baja perfusión (Low Perfusion):

Este es un modo especial con SpO₂ = 99%, PR = 80 bpm e índice de perfusión = 2.0 (al igual que los demás); este simula condiciones de mala circulación periférica como en vasoconstricción, con el objetivo de que el monitor debe demostrar su capacidad para medir SpO₂ y HR con señal de baja amplitud.


### C) Tolerancias o errores máximos permitidos (EMP) para cada parámetro fisiológico

Los errores máximos permitidos (EMP) para monitores de signos vitales están definidos por normas internacionales (ISO, IEC) y por las especificaciones técnicas de los fabricantes. A continuación, se presentan las tolerancias para la frecuencia cardíaca (HR) y la saturación de oxígeno (SpO₂), que son los dos parámetros principales del OxSim, a corde a la normativa ISO establacida: [4]

#### 1. EMP Frecuencia de pulso (PR / HR):

Acorde a la norma ISO 80601‑2‑61 para monitores, el EMP correspode a ±3 bpm o ±3% del valor real (el que sea mayor) en condiciones normales y sin movimiento, de hecho, el mismo manual de servicio del monitor indica este mismo valor en la sección A.8.5, y con un error de ±5 bpm con movimiento. Cabe resaltar que el error de la frecuencia generada por el simulador es inferior a 1 lpm.

#### 2. EMP Saturación de oxígeno (SpO₂):

Según la misma norma ISO 80601‑2‑61, el EMP corresponde a ±2% en adultos y pediátricos, y ±3% en neonatos a causa de la hemoglobina fetal; con unn rango entre 70 – 100%, teniendo en cuenta que no hay movimiento, de haberlo en se incrementa ±1% a los valores anteriores. El manual de servicio, en su sección A.8.4 también establece esos mismos valores; y el OxSim delega ese valor al propio sensor del monitor (los anteriores especificados).

#### 3. EMP Perfusión (Low Perfusion):

No existe un error numérico para la perfusión, porque es una condición de prueba cualitativa, asi que muestra los valores de condición fijados (SpO₂ = 99%, PR = 80 bpm y PI = 2.0), por lo que sus EMP se rigen los mismos valores explicados con anterioridad.

Cabe mencionar que los  EMP anteriores se refieren a la exactitud del monitor cuando recibe una señal de entrada correcta, es decir, asuminedo que el simulador OxSim debe estar calibrado correctamente para que sus señales de salida sean precisas.


## III. METODOLOGÍA EXPERIMENTAL



## IV. ANÁLISIS DE RESULTADOS



## V CONCLUSIONES



## VI. BIBLIOGRAFÍA

[1] Alejandra Cárdenas, “Simulación y Monitoreo de Variables Cardiovasculares y Hemodinámicas” Laboratorio de Instrumentación Biomédica y Biosensores, UMNG, 2025.

[2] Shenzhen Mindray Bio-Medical Electronics Co., Ltd., "BeneHeart D30/D20 Instructions for Use", Rev. 1.0, Shenzhen, China, Jun. 2022. 

[3] Medical IT, “OxSim – Pulse Oximeter Simulator – Ficha técnica,” Medical IT Colombia, 2019. 

[4] International Organization for Standardization, ISO 80601‑2‑61:2017 – Medical electrical equipment – Part 2‑61: Particular requirements for basic safety and essential performance of pulse oximeter equipment, Geneva, Switzerland: ISO, 2017.
















