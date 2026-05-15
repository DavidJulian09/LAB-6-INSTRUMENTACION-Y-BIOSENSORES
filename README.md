# LAB 6: SIMULACIÓN Y MONITOREO DE VARIABLES CARDIOVASCULARES Y HEMODINÁMICAS

## I. INTRODUCCIÓN

En un entorno clínico, es fundamental contar con equipos capaces de monitorear variables fisiológicas específicas, tales como la frecuencia cardíaca (HR) y la saturación periférica de oxígeno (SpO2) de forma continua; y no solo se limita en el monitoreo, sino que se requiere de equipos capaces de generar alarmas cuando las señales fisiológicas de los pacientes salen de los parámetros estables y que, en consecuencia, simbolizan un riesgo inmediato al paciente. Por lo anterior, se requieren de equipos especializados en simular patologías particulares, como arritmias e hipóxia, con el objetivo de que estos equipos pongan a prueba la capcidad diagnostica y de alerta de otros como lo es el monitor de signos vitales. [1]

Justamente el caso anterior es el que se pondrá a prueba en el presente laboratorio, haciendo uso de un simulador Pronk OxSim, distribuidos por Medical IT y compatible con pulsoxímetros, se evaluará la funcionalidad y presición de un monitor de signos vitales uMEC 100 (MINDRAY) presente en el laboratorio, todo mediante el desarrollo de los siguientes objetivos: [1]

### Objetivo general:

Operar con el simulador Pronk OxSim (OX-1) y el monitor de signos vitales uMEC 100 para pruebas funcionales.

### Objetivos específicos:

• Identificar los modos de operación de un simulador de parámetros hemodinámicos (Pronk OxSim).

• Verificar los límites de medición de un monitor de signos vitales mediante simulación de variables hemodinámicas.

• Interpretar variaciones en los parámetros hemodinámicos asociadas a estados fisiológicos y patológicos.


## II. MARCO TEÓRICO

### A) Modo "monitor" en el uMEC 100

El BeneHeart D30 es un equipo múltiple funciones que integra monitorización de signos vitales, desfibrilación, marcapasos externo, alertas, entre otros; el modo "monitor" es el estado operativo en el que el equipo actúa exclusivamente como monitor de parámetros fisiológicos (ECG, SpO₂, NIBP, CO₂, respiración...), es decir, es el modo estándar para la vigilancia continua del paciente. Como otras caracteísticas de este modo, es la presencia de alarmas fisiológicas y técnicas completamente configurables en cada parámetro [2]. Ahora bien, el procedimiento paso a paso para entrar en modo “Monitor” es simple, pues es el modo que está pre-establecido al momento de iniciar el equipo, si se desea agregar otros ajustes al modose selecciona en la pantalla tactil la opción monitor cerca de la esquina superior izquierda, donde se mostrarán más opciones como se muestra a continuación: 

<img width="1600" height="1204" alt="image" src="https://github.com/user-attachments/assets/2b93ee16-041b-4b3d-87d3-6b9a6409be43" />

_(Fig 1. Ajuste a modo monitor.)_

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

<img width="1204" height="1600" alt="image" src="https://github.com/user-attachments/assets/e9b58e9b-2bd1-40d0-b56e-604963274b19" />

_(Fig 2. Simulador OxSim OX-1.)_


### C) Tolerancias o errores máximos permitidos (EMP) para cada parámetro fisiológico

Los errores máximos permitidos (EMP) para monitores de signos vitales están definidos por normas internacionales (ISO, IEC) y por las especificaciones técnicas de los fabricantes. A continuación, se presentan las tolerancias para la frecuencia cardíaca (HR) y la saturación de oxígeno (SpO₂), que son los dos parámetros principales del OxSim, a corde a la normativa ISO establacida: [4]

#### 1. EMP Frecuencia de pulso (PR / HR):

Acorde a la norma ISO 80601‑2‑61 para monitores, el EMP correspode a ±3 bpm o ±3% del valor real (el que sea mayor) en condiciones normales y sin movimiento, de hecho, el mismo manual de servicio del monitor indica este mismo valor, y con un error de ±5 bpm con movimiento. Cabe resaltar que el error de la frecuencia generada por el simulador es inferior a 1 lpm.

#### 2. EMP Saturación de oxígeno (SpO₂):

Según la misma norma ISO 80601‑2‑61, el EMP corresponde a ±2% en adultos y pediátricos, y ±3% en neonatos a causa de la hemoglobina fetal; con unn rango entre 70 – 100%, teniendo en cuenta que no hay movimiento, de haberlo en se incrementa ±1% a los valores anteriores. El manual de servicio, también establece esos mismos valores; y el OxSim delega ese valor al propio sensor del monitor (los anteriores especificados).

#### 3. EMP Perfusión (Low Perfusion):

No existe un error numérico para la perfusión, porque es una condición de prueba cualitativa, asi que muestra los valores de condición fijados (SpO₂ = 99%, PR = 80 bpm y PI = 2.0), por lo que sus EMP se rigen los mismos valores explicados con anterioridad.

Cabe mencionar que los  EMP anteriores se refieren a la exactitud del monitor cuando recibe una señal de entrada correcta, es decir, asuminedo que el simulador OxSim debe estar calibrado correctamente para que sus señales de salida sean precisas.


## III. METODOLOGÍA EXPERIMENTAL

<img width="1449" height="1289" alt="image" src="https://github.com/user-attachments/assets/373c2e85-4e3a-4864-a8e7-2aa30493a54b" />

_(Fig 3. Ubicación PPG en el  OxSim OX-1.)_

### A) Simulación paciente bradicardia (40 bpm, SpO2 = 95%) 

<img width="1600" height="1204" alt="image" src="https://github.com/user-attachments/assets/849b7dc1-c820-474e-b52f-f2cb6a820394" />

_(Fig 4. Monitor simulación bradicardia.)_

<img width="1318" height="262" alt="image" src="https://github.com/user-attachments/assets/1c5366a6-426d-4596-a2b1-c6ce4e8e7637" />

_(Fig 5. Tabla de errores simulación bradicardia.)_


### B) Simulación paciente hipoxemia (80 bpm, SpO2 = 85%) 

<img width="1600" height="1204" alt="image" src="https://github.com/user-attachments/assets/424f53cc-2e75-4e9f-8a3b-82c6745a772b" />

_(Fig 6. Ajuste alarma límite inferior SpO2 a 90%.)_

<img width="1600" height="1131" alt="image" src="https://github.com/user-attachments/assets/59d14645-93af-41d8-b151-99bd757202ae" />

_(Fig 7. Monitor simulación hipoxemia.)_

<img width="1187" height="238" alt="image" src="https://github.com/user-attachments/assets/14640e87-32ff-4eb0-9ba1-ff3ef7130abf" />

_(Fig 8. Tabla de errores simulación hipoxemia.)_



### C) Simulación paciente low perf (SpO2 = 99%)

<img width="1600" height="1228" alt="image" src="https://github.com/user-attachments/assets/a6a61e04-77ff-44d4-9b1c-ba85d010860b" />

_(Fig 9. Ajuste alarma límite superior SpO2 a 97%.)_

<img width="1600" height="1070" alt="image" src="https://github.com/user-attachments/assets/cd0858b8-5709-433e-9b74-aa4b7ae8d09a" />

_(Fig 10. Monitor simulación low perf.)_

<img width="1188" height="238" alt="image" src="https://github.com/user-attachments/assets/ba4eea26-8d39-4bd4-ad08-628797c9f164" />

_(Fig 11. Tabla de errores simulación low perf.)_


### D) Simulación paciente taquicardia (140 bpm, SpO2 = 98%)

<img width="1600" height="1127" alt="image" src="https://github.com/user-attachments/assets/0ef5ae19-07f3-4cdd-b2b5-e8bc7ef64f3d" />

_(Fig 12. Monitor simulación taquicardia.)_

<img width="1191" height="241" alt="image" src="https://github.com/user-attachments/assets/06aa2896-cc54-4f2f-9fcd-ff1b68876398" />

_(Fig 13. Tabla de errores simulación taquicardia.)_



## IV. ANÁLISIS DE RESULTADOS



## V CONCLUSIONES



## VI. BIBLIOGRAFÍA

[1] Alejandra Cárdenas, “Simulación y Monitoreo de Variables Cardiovasculares y Hemodinámicas” Laboratorio de Instrumentación Biomédica y Biosensores, UMNG, 2025.

[2] S. Mindray Bio-Medical Electronics Co., Ltd., “Patient Monitor Operator’s Manual,” uMEC 60/uMEC 70/uMEC 80/uMEC 100/uMEC 120/uMEC 150, Rev. 2.0, Jul. 2023.

[3] Medical IT, “OxSim – Pulse Oximeter Simulator – Ficha técnica,” Medical IT Colombia, 2019. 

[4] International Organization for Standardization, ISO 80601‑2‑61:2017 – Medical electrical equipment – Part 2‑61: Particular requirements for basic safety and essential performance of pulse oximeter equipment, Geneva, Switzerland: ISO, 2017.
















