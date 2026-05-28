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

El uMEC 100 es un equipo múltiple funciones que integra monitorización de signos vitales, desfibrilación, marcapasos externo, alertas, entre otros; el modo "monitor" es el estado operativo en el que el equipo actúa exclusivamente como monitor de parámetros fisiológicos (ECG, SpO₂, NIBP, CO₂, respiración...), es decir, es el modo estándar para la vigilancia continua del paciente. Como otras caracteísticas de este modo, es la presencia de alarmas fisiológicas y técnicas completamente configurables en cada parámetro [2]. Ahora bien, el procedimiento paso a paso para entrar en modo “Monitor” es simple, pues es el modo que está pre-establecido al momento de iniciar el equipo, si se desea agregar otros ajustes al modose selecciona en la pantalla tactil la opción monitor cerca de la esquina superior izquierda, donde se mostrarán más opciones como se muestra a continuación: 

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

Habiendo desarrollado los conceptos teóricos requeridos, proseguimos con la simulación de los párametros, para lo anterior, hay que recordar que el OxSim OX‑1 es un simulador óptico que contiene un LED rojo y otro infrarrojo que emiten luz a través de una cavidad donde se coloca el sensor de pulsioximetría del uMEC 100, asegurándose de que el dedal cubra completamente la ventana óptica del simulador, tal como se obserga en la figura 3. Una vez ubicado el sensor de SpO₂ en el OxSim, se prosigue a configurar el modo que se desea simular con los valores preestablecidos, esto es tan sencillo como presionar el botón "MODE" de la parte frontal del OxSim, donde un LED indica el modo seleccionado, todo lo anterior se muestra en la siguiente figura:

<img width="1449" height="1289" alt="image" src="https://github.com/user-attachments/assets/373c2e85-4e3a-4864-a8e7-2aa30493a54b" />

_(Fig 3. Ubicación PPG en el OxSim OX-1.)_

Ya sabiendo cómo modificar los parámetros de simulación, se puede proseguir a tomar los datos correspondientes del monitor de signos. En el presente laboratorio trabajaremos con cuatro simulaciones con estados de pacientes distintos, los cuales son bradicardia, hipoxemia, baja perfución y taquicardia; en cada uno de los mencionados casos se tomarán 5 datos de registro cada 10 segundos, correspondientes a la frecuencia cardiaca y saturación de oxígeno en el monitor, estos datos se compararán con el valor "teórico" proveniente del OxSim para posteriormente determinar el error absoluto y porcentual de la toma de datos por medio de sus correspondientes ecuaciones, estos dos valores son fundamentales pues nos permiten evaluar si el monitor cumple con las tolerancias clínicas establecidas y la presición del mismo, así como el estado y funcionalidad del mismo en caso de que sea requerido la calibración del monitor.

<img width="168" height="40" alt="image" src="https://github.com/user-attachments/assets/6f320f92-b521-4302-b47d-56119e9e003d" />

_(Ecuación 1. Cálculo error absoluto.)_

<img width="260" height="72" alt="image" src="https://github.com/user-attachments/assets/36d6e058-562c-4f15-bdae-70e7a7527e7b" />

_(Ecuación 2. Cálculo error porcentual.)_


### A) Simulación paciente bradicardia (40 bpm, SpO₂ = 95%) 

Como primer simulación se seleccionaron los datos correspondientes a los de un paciente con bradicardia, con una frecuancia muy baja (40 bpm), que se refelja en la pantalla del monitor (fig. 4) donde las ondas se encuentran muy separadas entre sí; por otro lado, la amplitud de la onda es normal, pues posee un valor de saturación corriente (95%). Lo anterior se evidencia en que la PPG tiene un ascenso rápido correspondiente a la pendiente sistólica, y en lugar de tener un breve valle entre los picos sistólicos y diastólicos para posteriormennte tener un descenso rápido, posee una gran meseta en donde la fase diastólica dura más de lo normal a causa de la bradicardia del "paciente"tal como se evidencia a continuación:

<img width="1600" height="1204" alt="image" src="https://github.com/user-attachments/assets/849b7dc1-c820-474e-b52f-f2cb6a820394" />

_(Fig 4. Monitor simulación bradicardia.)_

Como punto a resaltar, se evidencia una alarma en la parte superior de la pantalla que indica un ritmo cardiaco bajo. Habiendo explicado el comportamiento de la onda PPG, se prosigue con el análisis del error de las medidas, tal como se evidencia en la figura 5, el monitor midió la frecuencia de pulso con una exactitud perfecta (error cero) en todas las repeticiones; por otro lado el monitor mostró una lectura de SpO₂ un punto por encima del valor simulado en todas las mediciones, este error absoluto de 1,05% está dentro de la tolerancia clínica aceptable, que es de ±2% para pacientes adultos y ±3% para neonatos. Analizando el error correspondiente del SpO₂, se cree que es simplemente un error sistemático que se puede deber a una leve descalibración.

<img width="1318" height="262" alt="image" src="https://github.com/user-attachments/assets/1c5366a6-426d-4596-a2b1-c6ce4e8e7637" />

_(Fig 5. Tabla de errores simulación bradicardia.)_


### B) Simulación paciente hipoxemia (80 bpm, SpO₂ = 85%) 

Proseguimos con el siguiente caso a simular, hipoxemia (baja saturación de oxígeno), pero primero calibramos una alarma para alertar de los valores de SpO₂, esta alarma se configura en el espacio mencionado en la sección II.A, como se muestra en la figura 6, la configuración permite establecer los límites superiores (alto) e inferiores (bajo), estas alarmas se pueden ajustar al valor deseado y se les puede asignar valores de prioridad, siendo amarillo prioridad media y rojo prioridad alta; sabiedno lo anterior y que se busca simular los datos de un paciente con bajo SpO2 (85%), se estableció la alarma inferior en 90%, de forma que alerte en el momente que se registre una saturación inferior a dicho valor

<img width="1600" height="1204" alt="image" src="https://github.com/user-attachments/assets/424f53cc-2e75-4e9f-8a3b-82c6745a772b" />

_(Fig 6. Ajuste alarma límite inferior SpO₂ a 90%.)_

Ya habiendo configurado la alarma se monitoreó la señal PPG resultante del monitor, como se observa en la figura 7, la frecuencia es visiblemente mayor en comparación a la simulación anterior, siendo una frecuencia propia de un paciente sano, por dicha razón se puede evidenciar una señal PPG corriente, con una clara diferenciación de la fase sistólica con la diastólica sin una meseta extensa como en el caso previo. Adicionalmente, en la imagen del monitor se evidencia el sistema de alerta en consecuencia al ajuste anteriormente realizado, mostrando un recuadro intermitente amarillo que resalta el valor de SpO₂ acompañado de un sonido intermitente de alerta, el cual se activo antes de los 5 segundos después del inicio de la prueba.

<img width="1600" height="1131" alt="image" src="https://github.com/user-attachments/assets/59d14645-93af-41d8-b151-99bd757202ae" />

_(Fig 7. Monitor simulación hipoxemia.)_

Respecto a los errores, al igual que en el caso de bradicardia, el monitor midió la frecuencia de pulso con exactitud perfecta, además, en esta simulación el monitor reprodujo exactamente el valor simulado de 85% en todas las mediciones, indicando el buen funcionamiento tanto el sistema metrológico como el de alertas propias del monitor.

<img width="1187" height="238" alt="image" src="https://github.com/user-attachments/assets/14640e87-32ff-4eb0-9ba1-ff3ef7130abf" />

_(Fig 8. Tabla de errores simulación hipoxemia.)_



### C) Simulación paciente low perf (SpO₂ = 99%)

Para el siguiente caso a simular, en donde un paciente padece de baja perfusión, se configuró nuevamente una alarma para el monitoreo del SpO₂, con la diferencia de que en este caso no se ajustó el límite inferior sino el superior, decidiendo establecer el valor en 97% tal como se evidencia en la figura 9. Al igual que la alarma inferior, a esta también se le asignó una prioridad media.

<img width="1600" height="1228" alt="image" src="https://github.com/user-attachments/assets/a6a61e04-77ff-44d4-9b1c-ba85d010860b" />

_(Fig 9. Ajuste alarma límite superior SpO₂ a 97%.)_

En esta onda de PPG lo primero a resaltar es el pulso cardiaco de 80 bpm, pues aunque el OxSim no detalla este valor como en los otros modos, es el valor que mantiene según su ficha técnica. Respecto a la forma de la onda, en un caso de baja perfusión el flujo sanguíneo periférico está disminuido ya sea por una vasoconstricción extrema o un fallo cardiaco, de modo que la amplitud de la onda se vuelve muy baja y se presentan deformaciones y ruido en la misma; sin embargo, lo anterior no se evidencia en la pantalla del monitor, esto se debe a que el OxSim no generan una onda PPG realista en términos de amplitud variable, simplemente produce una señal óptica de amplitud constante que el monitor interpreta; como otra opción de la razón de la onda es que el monitor aplica una ganancia automática que estandariza la amplitud visual de la onda. Por todo lo anterior el comportamiento de la onda es casi idéntico al presentado en la simulación de hipoxemia, para simular un estado verdadero de baja perfusión se requiere de otro simulador distinto del OxSim. Finalmente acorde al ajuste de la alrma superior de SpO₂, se muestra el recuadro y sonido de alerta en el panatalla tal como se muestra en la figura 10.

<img width="1600" height="1070" alt="image" src="https://github.com/user-attachments/assets/cd0858b8-5709-433e-9b74-aa4b7ae8d09a" />

_(Fig 10. Monitor simulación low perf.)_

A pesar de lo anterior, los valores registrados fueron precisos, los pulsos por minuto mantienen el valor establecido de 80 bpm, si embargo, el valor de saturación muestra un error absoluto de 1, que a su vez indica un error porcental del 1% (figura 11), este resultado aún está dentro de la toleracia clínica establecida, y no solo eso, sino que en casos de baja perfusión algunos monitores tienen problemas para mantener la onda y los valores estables, por lo que el hecho de que haya sido capás de mantener dichos parámetros es un indicador de buen rendimiento.

<img width="1188" height="238" alt="image" src="https://github.com/user-attachments/assets/ba4eea26-8d39-4bd4-ad08-628797c9f164" />

_(Fig 11. Tabla de errores simulación low perf.)_


### D) Simulación paciente taquicardia (140 bpm, SpO₂ = 98%)

Para el último caso a simular, se tomaron los datos de un paciente con taquicardia, este caso tal como se muestra en la figura 12 se refleja con una frecuencia de las ondas mayor a todos los casos anteriores. Lo que más destaca sin duda es la usencia de la parte diastólica de la señal, mostrando únicamente picos agudos sistólicos a causa de la reducción del tiempo de llenado diastólico; en cuanto a la amplitud de la señal se mantiene en los mismos rangos que las simulaciones anteriores. Como información adicional, en la pantalla se muestran las alarmas de alerta (recuadros amarillos) tanto para el valor de la frecuencia cardiaca como para el valor de SpO₂, pues superan los límites estabecidos en la sección de alarmas.

<img width="1600" height="1127" alt="image" src="https://github.com/user-attachments/assets/0ef5ae19-07f3-4cdd-b2b5-e8bc7ef64f3d" />

_(Fig 12. Monitor simulación taquicardia.)_

Finalmente, el monitor midió la frecuencia de 140 bpm con exactitud perfecta en todas las tomas (error 0), indicando que el monitor permite la detección de picos incluso en alta frecuencia, con este resultado y todos los anteriores se evidencia que el monitor no posee error ninguno en el cálculo de la frecuancia cardiaca. En cuanto a los resultados de saturación de oxígeno, en tres de las cinco mediciones el monitor fue exacto, y en dos tomas hubo un error de 1,02%; esto se puede deber a que la taquicardia puede afectar ligeramente el cálculo de SpO₂ en algunos monitores, dificultando al mismo tiempo en encontrar el punto exacto del pico diastólico. 


<img width="1192" height="241" alt="image" src="https://github.com/user-attachments/assets/3c0ec03b-b41a-445e-8e80-b642329180b1" />

_(Fig 13. Tabla de errores simulación taquicardia.)_

En cualquier caso, el error presentado es clínicamente insignificante, tanto en esta simulación como en las anteriores, pues se encuentra dentro de la tolerancia clínica permitida por la norma ISO 80601‑2-61(±2% para adultos), por tanto, el monitor es clínicamente fiable para los rangos simulados, sin contar que es capás de mantener un sistema de alerta fiable en todo momento.


## IV. ANÁLISIS DE RESULTADOS

### A) Evaluación estadística de las diferencias entre los valores simulados por el OxSim y los mostrados por el monitor uMEC 100

Para este primer análisis buscamos cuantificar  la exactitud del monitor al medir la frecuencia cardíaca (HR) y la saturación de oxígeno (SpO₂) en los modos descritos en la sección anterior, de forma que se buscará evaluar los parámetros de error absoluto medio (MAE), error porcentual medio (MPE), desviación estandar del error y el máximo error absoluto. Todo lo anterior se evidencia en la siguiente tabla:

<img width="957" height="430" alt="image" src="https://github.com/user-attachments/assets/46c66896-a79e-4e09-8e98-c9c682c0cd37" />

_(Fig 14. Tabla resultados estadísticos.)_

Lo primero a resaltar de la tabla anterior es que el monitor mostró una exactitud perfecta en la medición de la frecuencia de pulso, tal como se evidenció en la metodología, por tanto, el monitor es altamente fiable para la frecuencia de pulso. Por otra parte, se puede evidenciar un leve error estadístico entre los valores simulados y medidos de la saturación de oxígeno, en donde en los casos de bradicardia y baja perfusión el error sistemático de 1%, con un sesgo constante reflajanddo en que la desviación es 0; en el caso de la taquicardia el error medio es bajo (0,4%) aunque con cierta variabilidad (desviación de 0,55), aún así el error máximo de 1% sigue siendo aceptable; finalmente es de resaltar que en la simulación de hipoxemia, el error fue de 0 demostrando una exactitud excelente.

Conoforme a lo anterior se puede analisar que las diferencias entre los valores simulados y los medidos no son estadísticamente significativas (son inferiores a las tolerancias normativas), de modo que el monitor uMEC 100 demuestra un rendimiento óptimo para su uso clínico en la monitorización de HR y SpO₂.

### B) Relación entre la forma de onda visualizada en el monitor y la frecuencia cardíaca / saturación de oxígeno

La onda PPG es una representación gráfica del volumen sanguíneo pulsátil en los capilares de los dedos, mostrando una onda que consta de un ascenso sistólico y un descenso diastólico, por esa razón la frecuencia de los picos de la onda PPG es idéntica a la frecuencia cardíaca, en la pantalla del monitor se puede contar los picos por unidad de tiempo o confiar en el valor numérico de HR que el monitor calcula automáticamente a partir de la distancia entre picos (intervalo R‑R de las sístoles en el ECG). Esto se evidencia pues en la simulación de bradicardia los picos de los pulsos se encuentran muy separados entre sí, mostrando una onda lenta, con un largo periodo diastólico; por el contrario, en la simulación de taquicardia, los picos están muy juntos provocando que la onda se comprima perdiendo la correcta visualización del periodo diastólico

En cuanto a la relación de la onda con la saturación de oxígeno (SpO₂), hay que recordar que este parámetro se calcula a partir de la relación entre las absorciones de luz roja (660 nm) e infrarroja (940 nm) en los picos y valles de la onda PPG, donde la variación pulsátil de volumen sanguíneo permite aislar la absorción de la sangre arterial de la de los tejidos fijos. Recordando lo anterior se debe de establecer algo, la forma de la onda PPG no es un indicador directo de la SpO₂, puede haber dos ondas con la misma forma pero con saturación distinta, lo anterior se evidencia comparando las simulaciones de hipoxemia y de baja perfusión, en donde la forma de la onda es la misma a pesar de que la saturación de la primera es 85% y el de la segunda es 99%, manteniendo la misma frecuencia pulsatil en ambas simulaciones; sin embargo, para que el valor de SpO₂ sea influyente en la onda PPG, debe tener valores muy bajos (<70%), provocando una disminución de la amplitud de la onda. [5]

### C) Cuál es el principio de operación del Pronk OxSim OX-1 para simular una onda pulsátil?

Tal como se ha explicado con anterioridad el OxSim OX-1 es un simulador óptico que modula la intensidad de las fuentes de luz de los LED rojo e infrarrojo del pulsoxímetro para imitar los cambios de volumen sanguíneo arterial durante el ciclo cardíaco. Explicando más a fondo, en  un paciente real, la luz que atraviesa un dedo es atenuada por tejidos (piel, hueso, venas) y por la sangre arterial pulsátil, la absorbancia varía con el tiempo debido al flujo pulsátil y la relación entre las absorbancias en las dos longitudes de onda permite calcular la SpO₂. En el OxSim, este fenómeno ocurre iniciando con la generación de la onda pulso mediante un microcontrolador interno que genera una señal eléctrica con una forma de onda típica de un PPG, posteriormente, la corriente que alimenta los LED rojo e infrarrojo se modula con la amplitud de la onda generada, dicha modulación entre los dos LED se ajusta para representar diferentes valores de SpO₂; todo lo  anterior permite la comunicación ótica entre el OxSim y el pulsoxímetro del monitor, el sensor mide la luz transmitida y su fotodetector convierte la intensidad luminosa en una señal eléctrica que el monitor interpreta como una PPG y a partir de la cual calcula SpO₂ y frecuencia de pulso. [6]

Ahora bien, aunque su principio de operación reproduce fielmente los parámetros numéricos de la pulsioximetría, como la frecuencia pulsátil y el SpO₂, no puede emular la morfología de la onda PPG en casos de baja perfusión, como se evidenció en la metodología experimental, ni otros parámetros dependientes del flujo sanguíneo. 


### D) ¿Por qué la SpO2 baja puede ser un falso positivo (falsa alarma) en una situación de mala perfusión?

Una falsa alarma de SpO₂ baja (hipoxemia) ocurre cuando el monitor indica una saturación por debajo del límite de alarma cuando la oxigenación arterial del paciente es normal, esto ocurre con frecuencia en pacientes con mala perfusión periférica (flujo sanguíneo reducido). Sabiendo lo anterior hay múltiples razones por las que se pueden producir estas falsas alarmas como: [7]

1. Una baja relación entre señal y ruido,por ejemplo, en mala perfusión el volumen sanguíneo pulsátil (componente AC de la PPG) es muy pequeño, haciendo que la absorción de los tejidos estáticos sea mayor; lo anterior provoca que el ruido eléctrico supere la señal real y el monitor interprete el ruido como un pulso débil, produciendo lecturas de SpO₂ erróneas.

2. El efecto de la vasoconstricción inducida por fármacos o hipotermia es un factor relevante también, pues en pacientes críticos a menudo reciben vasopresores (noradrenalina) para mantener la presión arterial, lo que provoca vasoconstricción periférica, esto a su vez reduce ampliamente la amplitud del PPG provocando que el monitor no detecte correctamente los pulsos, dando como resultado un falso positivo.

3. La mala perfusión a menudo acompaña a pacientes intubados, agitados o con temblores, por tanto el movimiento produce picos en la señal que se confunden con el pulso. Aunque los monitores tienen algoritmos que corrigen el error de movimiento, cuando la perfusión es baja, estos algoritmos pueden fallar y el monitor puede reportar una SpO₂ falsamente bajo.

4. Finalmente, afecta el sitio que se ubica el sensor de pulsoximetría, el sensor de dedo es el más común pero en mala perfusión los dedos son los primeros en vasoconstriccionarse, que descencadena en un error en el valor de SpO₂. Por la anterior razón en casos con mala perfusión se seleccionan otras zonas anatómicas como el lóbulo de la oreja o la frente, que son menos sensibles a la vasoconstricción.

Mantener un control de todos los puntos anteriores es fundamental, pues si no se es consciente de estas falsas alarmas puede provocar errores como la administración innecesaria de oxígeno u otras intervenciones no necesarias. Para mitigar estas consecuencias se debe de poseer un monitor capás de tener una lectura precisa del índice de perfusión, en dodne si este índice es menor al 0,5%, los médicos podran saber que las lecturas de SpO₂ no son fiables.


## V. CONCLUSIONES

Para concluir el presente laboratorio, se determinó que el monitor de signos vitales Mindray uMEC 100 es altamente confiable para la medición de la frecuencia cardíaca y la saturación periférica de oxígeno en las condiciones simuladas, pues posee un error de 0 al momento de medir frecuencia pulsátil, y un error de 1 punto porcentual en la saturación, siempre dentro del margen clínico aceptable de ±2 % para adultos; adicionalmente, la repetibilidad fue excelente teniendo una desviación estandar casi nula, demostrando que el monitor no presenta fallos intermitentes ni de calibración. 

En cuanto al simulador OxSim OX-1 para simular condiciones patológicas, aunque útil para pruebas funcionales básicas, presenta importantes limitaciones en sus capacidades, siendo la más destacable un estado de baja perfusión no realista, pues el OxSim no produjo una reducción apreciable de la amplitud de la onda PPG, ni ruido o inestabilidad; adicionalmente como otra limitante, el OxSim solo ofrece valores fijos de SpO₂ y frecuencias de pulso, impidiendo la simulasión de hipoxemia grave (70 % o 50 %), desaturaciones intermitentes, ni frecuencias cardíacas extremas, limitando la capacidad de evaluación del monitor en condiciones de alta complejidad.

Como última conclusión, en el presente laboratorio logramos comprender el principio de funcionamiento de un simulador de pulsioximetría y cómo se relaciona con la fisiología real, el cómo se aplica el cálculo de errores absolutos y porcentuales para evaluar la exactitud y presición de un monitor, la identificación de las limitaciones de los equipos de simulación y reconocer que la forma de onda PPG refleja directamente la frecuencia cardíaca pero no es un indicador visual de la SpO₂.


## VI. REFERENCIAS

[1] Alejandra Cárdenas, “Simulación y Monitoreo de Variables Cardiovasculares y Hemodinámicas” Laboratorio de Instrumentación Biomédica y Biosensores, UMNG, 2025.

[2] S. Mindray Bio-Medical Electronics Co., Ltd., “Patient Monitor Operator’s Manual,” uMEC 60/uMEC 70/uMEC 80/uMEC 100/uMEC 120/uMEC 150, Rev. 2.0, Jul. 2023.

[3] Medical IT, “OxSim – Pulse Oximeter Simulator – Ficha técnica,” Medical IT Colombia, 2019. 

[4] International Organization for Standardization, ISO 80601‑2‑61:2017 – Medical electrical equipment – Part 2‑61: Particular requirements for basic safety and essential performance of pulse oximeter equipment, Geneva, Switzerland: ISO, 2017.

[5] J. G. Webster, Ed., Design of Pulse Oximeters. Bristol, UK: Institute of Physics Publishing, 1997

[6] J. P. O’Leary, “The physiology of pulse oximetry: Beer‑Lambert law, oxygen‑hemoglobin dissociation curve, and calibration curves,” Journal of Clinical Monitoring and Computing, Feb. 2004.

[7] Fluke Biomedical, “Accuracy and reliability of pulse oximeters in low‑perfusion conditions: a systematic review,” Journal of Clinical Monitoring and Computing, Aug. 2020.
















