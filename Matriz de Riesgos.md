# Matriz de Riesgos – Open Hub Tec

**Proyecto:** Open Hub Tec – plataforma con blockchain para artesanas textiles de la Región Mixteca

**Asignatura:** Gestión de Proyectos de Software (SCG-1009) · Unidad 3 · Tema 3.5

**Metodología:** eduScrum

**Equipo:** Mari Cruz Gomez, Carla Bautista León, Alan Sahid Cortes, Aldair Gonzalez

---

## 1. Introducción y método

Este documento identifica, clasifica, evalúa y da respuesta a los riesgos de Open Hub Tec. Sigue las etapas de gestión de riesgos del PMI vistas en el tema 3.5:

| Etapa | Qué se hace aquí |
|---|---|
| 3.5.1 Identificación | Se listan los riesgos a partir de las historias de usuario, el Costo de la Calidad y el análisis de viabilidad |
| 3.5.2 Clasificación | Se agrupan en tres dimensiones: técnicos, sociales/operativos y financieros/Web3 |
| 3.5.3 Evaluación | Se asigna probabilidad e impacto y se calcula la severidad y la exposición |
| 3.5.4 Respuesta | Se define una estrategia (mitigar, evitar, transferir o aceptar), responsable y plan de contingencia |

### Escalas usadas

**Probabilidad**

| Nivel | Descripción | Probabilidad estimada |
|---|---|---|
| 1 | Muy baja | 10 % |
| 2 | Baja | 30 % |
| 3 | Media | 50 % |
| 4 | Alta | 70 % |
| 5 | Muy alta | 90 % |

**Impacto** (en horas extra de trabajo del equipo; costo de referencia $100 MXN/h)

| Nivel | Descripción | Horas extra |
|---|---|---|
| 1 | Muy bajo | hasta 2 h |
| 2 | Bajo | 3 a 5 h |
| 3 | Medio | 6 a 9 h |
| 4 | Alto | 10 a 14 h |
| 5 | Muy alto | 15 h o más, o daño que no se puede deshacer |

**Severidad** = Probabilidad × Impacto (valor de 1 a 25). **Exposición** = Probabilidad (%) × Impacto (horas).

| Severidad | Nivel |
|---|---|
| 1 a 4 | Bajo |
| 5 a 9 | Medio |
| 10 a 14 | Alto |
| 15 a 25 | Crítico |

---

## 2. Identificación y clasificación de riesgos

### 2.1 Riesgos técnicos (arquitectura y software)

| ID | Riesgo | Historias afectadas | Causa y vínculo con el proyecto |
|---|---|---|---|
| T1 | Falla en el guardado sin conexión o duplicados al sincronizar | HU-2.1 | La señal en comunidades de la Mixteca es intermitente y la HU-2.1 exige guardar local y sincronizar después |
| T2 | Se escriben en blockchain datos personales o fotos que no deberían ir en la cadena | HU-1.1, HU-1.2, HU-3.1 | Lo que se escribe en blockchain no se puede borrar; solo debe ir el hash y la marca de tiempo |
| T3 | Curva de aprendizaje de contratos inteligentes y de la red blockchain | HU-1.1, HU-1.2, HU-2.1 | El equipo está aprendiendo la tecnología durante el mismo periodo del desarrollo |
| T4 | Lentitud o caídas de la red de pruebas (testnet) | Todas | El desarrollo depende de redes de prueba externas |
| T5 | Las notificaciones de pedido no llegan sin internet | HU-3.2 | La notificación automática depende de conexión del comprador y de la artesana |
| T6 | El promedio de 12 meses incluye registros no confirmados | HU-2.1, HU-2.2 | Error de lógica al filtrar solo registros confirmados |

### 2.2 Riesgos sociales y operativos (organizaciones de la Mixteca y equipo)

| ID | Riesgo | Historias afectadas | Causa y vínculo con el proyecto |
|---|---|---|---|
| S1 | Poco acceso o disponibilidad de las artesanas para validar el sistema | Todas | Distancias largas, conectividad irregular y tiempos de las artesanas que no coinciden con los del Sprint |
| S2 | Baja adopción por desconfianza o poca familiaridad con blockchain y apps | HU-1.1, HU-2.1, HU-3.1 | Las usuarias pueden no ver el beneficio o no sentirse cómodas con tecnología nueva |
| S3 | Exposición de datos de artesanas o conflicto por autoría comunitaria | HU-1.1, HU-1.2 | Los reportes públicos pueden mostrar información sensible o registrar un diseño colectivo sin aval |
| S4 | Sobrecarga del equipo por seis historias en un solo periodo y otras materias | Todas | 142 h estimadas entre cuatro integrantes que también tienen otras clases |
| S5 | Celulares de gama básica con poca memoria o pantalla pequeña | HU-3.1, HU-3.2 | Las usuarias usarán el teléfono; fotos pesadas pueden volver lenta la app |

### 2.3 Riesgos financieros y Web3 (Stellar Community Fund y Drips Protocol)

| ID | Riesgo | Historias afectadas | Causa y vínculo con el proyecto |
|---|---|---|---|
| F1 | No ganar un premio del Stellar Community Fund (SCF) | Sostenibilidad posterior al curso | El SCF decide por votación de la comunidad; el financiamiento no está asegurado |
| F2 | Drips no se integra bien con una solución en Stellar | Sostenibilidad posterior al curso | La documentación de Drips lo describe para cadenas EVM; la integración con Stellar debe confirmarse |
| F3 | Cambio de valor del XLM entre la aprobación y el pago del premio | Sostenibilidad posterior al curso | Los premios del SCF se pagan en XLM |
| F4 | Comisiones de red e infraestructura en producción no previstas | Producción | En testnet cuestan $0, pero en una red real habría comisiones |
| F5 | Cambios en montos, fechas o reglas de las convocatorias | Sostenibilidad posterior al curso | Las rondas y requisitos del SCF y de Drips pueden cambiar |
| F6 | Costo de la calidad subestimado (las fallas externas superan las 4 h estimadas) | Todas | Si hay más defectos de los previstos, el CoQ del Sprint 2 (34 h, $3,400 MXN) se queda corto |

---

## 3. Evaluación de probabilidad, impacto y severidad

| ID | Riesgo (resumen) | Prob. (1–5) | % | Impacto (1–5) | Horas extra | **Severidad** | **Exposición (h)** | Nivel |
|---|---|---|---|---|---|---|---|---|
| T1 | Falla en guardado sin conexión / duplicados | 4 | 70 % | 5 | 16 h | **20** | **11.2** | Crítico |
| T2 | Datos personales o fotos escritos en la cadena | 2 | 30 % | 5 | 16 h | **10** | **4.8** | Alto |
| T3 | Curva de aprendizaje de blockchain | 4 | 70 % | 4 | 12 h | **16** | **8.4** | Crítico |
| T4 | Caídas o lentitud de la testnet | 3 | 50 % | 3 | 8 h | **9** | **4.0** | Medio |
| T5 | Notificaciones no llegan sin internet | 3 | 50 % | 3 | 6 h | **9** | **3.0** | Medio |
| T6 | Promedio con registros no confirmados | 2 | 30 % | 3 | 6 h | **6** | **1.8** | Medio |
| S1 | Poco acceso de las artesanas para validar | 4 | 70 % | 4 | 12 h | **16** | **8.4** | Crítico |
| S2 | Baja adopción por desconfianza o poca familiaridad | 3 | 50 % | 4 | 10 h | **12** | **5.0** | Alto |
| S3 | Exposición de datos / conflicto de autoría comunitaria | 2 | 30 % | 5 | 16 h | **10** | **4.8** | Alto |
| S4 | Sobrecarga del equipo | 4 | 70 % | 4 | 14 h | **16** | **9.8** | Crítico |
| S5 | Celulares de gama básica | 3 | 50 % | 3 | 6 h | **9** | **3.0** | Medio |
| F1 | No ganar el premio del SCF | 4 | 70 % | 3 | 8 h | **12** | **5.6** | Alto |
| F2 | Drips no se integra con Stellar | 3 | 50 % | 3 | 8 h | **9** | **4.0** | Medio |
| F3 | Variación del valor del XLM | 3 | 50 % | 2 | 4 h | **6** | **2.0** | Medio |
| F4 | Comisiones e infraestructura no previstas | 2 | 30 % | 3 | 6 h | **6** | **1.8** | Medio |
| F5 | Cambios en reglas de SCF / Drips | 2 | 30 % | 2 | 4 h | **4** | **1.2** | Bajo |
| F6 | CoQ subestimado | 3 | 50 % | 3 | 8 h | **9** | **4.0** | Medio |

**Exposición total bruta:** 82.8 h (antes de aplicar respuestas). Por dimensión: técnicos 33.2 h, sociales/operativos 31.0 h, financieros/Web3 18.6 h.

### Priorización

Los cinco riesgos con mayor exposición son T1 (11.2 h), S4 (9.8 h), T3 (8.4 h), S1 (8.4 h) y F1 (5.6 h). Juntos suman 43.4 h, cerca del 52 % de la exposición total, así que las respuestas se atienden primero en ese orden.

### Matriz de calor (probabilidad × impacto)

| Probabilidad \ Impacto | 1 | 2 | 3 | 4 | 5 |
|---|---|---|---|---|---|
| **5 (90 %)** | | | | | |
| **4 (70 %)** | | | F1 | T3, S1, S4 | **T1** |
| **3 (50 %)** | | F3 | T4, T5, S5, F2, F6 | S2 | |
| **2 (30 %)** | | F5 | T6, F4 | | T2, S3 |
| **1 (10 %)** | | | | | |

---

## 4. Estrategias de respuesta

Estrategias posibles: **mitigar** (reducir probabilidad o impacto), **evitar** (cambiar el plan para que no ocurra), **transferir** (pasar el riesgo a un tercero) y **aceptar** (asumirlo y tener un plan por si pasa).

### 4.1 Riesgos críticos y altos

| ID | Estrategia | Acciones preventivas | Plan de contingencia | Responsable | Disparador / indicador |
|---|---|---|---|---|---|
| T1 | Mitigar | Hacer un prototipo temprano del guardado local y la sincronización; usar identificadores únicos por venta para evitar duplicados; probar sin conexión desde el primer sprint | Si el prototipo falla, reducir la HU-2.1 a "guardar local y sincronizar manualmente con un botón" y documentarlo como mejora | Carla Bautista León | Más de 2 duplicados o pérdidas en las pruebas de sincronización |
| S4 | Mitigar | Priorizar las historias de prioridad Alta; revisar horas reales cada semana en el tablero; repartir la carga equitativamente (34 a 36 h por persona) | Reducir el alcance: dejar la HU-2.2 para después o trabajar una sola problemática | eduScrum Master [Nombre], con todo el equipo | Horas reales superan lo estimado en más del 20 % en dos semanas seguidas |
| T3 | Mitigar | Reservar las primeras sesiones para tutoriales y ejemplos oficiales; trabajar en pareja en la parte de contratos; empezar con la HU-1.1 como práctica | Usar un registro más simple (hash y fecha) sin lógica avanzada en el contrato | Mari Cruz Gomez | Una tarea de blockchain lleva el doble de lo estimado |
| S1 | Mitigar | Pedir validación con anticipo y por mensajes o llamadas cuando no se pueda ir; concentrar las preguntas en pocas sesiones; documentar las respuestas como evidencia | Validar con casos de prueba simulados basados en las historias y retomar con las artesanas en la siguiente oportunidad | Alan Sahid Cortes (contacto con la organización) | Dos semanas sin respuesta o sin sesión de validación |
| F1 | Mitigar y aceptar | No depender del premio para terminar el curso; preparar la postulación al SCF con lo que se avance; confirmar fechas de la ronda vigente | Buscar apoyo institucional, recursos propios y herramientas gratuitas; seguir con testnet | Aldair Gonzalez | Se cierra la ronda sin postulación lista, o se recibe respuesta negativa |
| S2 | Mitigar | Interfaz sencilla, mensajes claros y capacitación breve; explicar blockchain solo como "sello que no se puede cambiar" | Material de apoyo y acompañamiento de una persona de la organización | Alan Sahid Cortes | Artesanas que no logran registrar sin ayuda en la prueba de usabilidad |
| T2 | Evitar | Regla de diseño: solo hash y timestamp en la cadena; revisar cada registro en pruebas antes de pasar a Done | Si se detecta en testnet, descartar el contrato y reiniciar con los datos corregidos (nunca en red real) | Mari Cruz Gomez | Cualquier campo con datos personales en la transacción |
| S3 | Evitar y mitigar | Privacidad por defecto en los reportes; aval comunitario obligatorio; confirmar autorización antes de mostrar datos | Retirar el reporte público y generar una versión sin datos sensibles | Mari Cruz Gomez | Una prueba de HU-1.2 muestra datos personales sin autorización |

### 4.2 Riesgos medios y bajos

| ID | Estrategia | Acciones preventivas | Plan de contingencia | Responsable |
|---|---|---|---|---|
| T4 | Aceptar y mitigar | Guardar los contratos y datos de prueba en GitHub para poder reiniciar rápido | Trabajar en otra tarea o en un entorno local mientras se recupera la red | Mari Cruz Gomez |
| T5 | Mitigar | Mostrar el estado dentro de la app y guardar la notificación pendiente para enviarla cuando haya señal | Aviso manual por mensaje a las partes | Alan Sahid Cortes |
| T6 | Mitigar | Prueba con datos conocidos y filtro explícito por estado "confirmado" | Corregir el filtro y repetir la prueba (cuenta como corrección en el CoQ) | Aldair Gonzalez |
| S5 | Mitigar | Comprimir fotos, limitar el tamaño de carga y probar en un teléfono de gama básica | Reducir a una sola foto por registro | Alan Sahid Cortes |
| F2 | Mitigar | Revisar la documentación oficial de Drips y probar una integración mínima antes de incluirlo en el plan | Dejar Drips como mejora futura y apoyarse en el SCF y recursos institucionales | Aldair Gonzalez |
| F3 | Aceptar | Considerar la variación al calcular el presupuesto de producción y no comprometer gastos antes de recibir el pago | Ajustar el alcance de producción al monto recibido | Aldair Gonzalez |
| F4 | Mitigar | Estimar las comisiones con la información de la red antes de pasar a producción | Pausar el paso a producción hasta tener el monto cubierto | Carla Bautista León |
| F5 | Aceptar | Revisar las convocatorias vigentes antes de cada decisión | Ajustar el plan de sostenibilidad a las nuevas reglas | Aldair Gonzalez |
| F6 | Mitigar | Registrar las horas reales de prevención, evaluación y corrección en el tablero | Recalcular el CoQ y avisar al Product Owner si se rebasan las 34 h | Aldair Gonzalez |

---

## 5. Coherencia con los sprints anteriores y con eduScrum

| Insumo | Cómo se conecta con la matriz |
|---|---|
| Sprint 1 – Historias de usuario auditadas | Cada riesgo señala la historia afectada (HU-1.1 a HU-3.2). Los riesgos T1, T2, T5, T6 y S3 salen de los criterios de aceptación de esas historias |
| Sprint 2 – Costo de la Calidad (34 h, $3,400 MXN) | Las acciones preventivas se cargan a las 12 h de prevención y las correcciones a las 8 h de corrección; F6 vigila que las 4 h de fallas externas no se rebasen |
| Sprint 3 – Viabilidad y tablero | Los riesgos S4, T1 y F1 respaldan el dictamen GO condicionado; las 142 h y los $14,200 MXN del tablero son la base de las exposiciones |
| eduScrum | Cada riesgo tiene responsable dentro del equipo y se revisa en las reuniones de seguimiento y en la retrospectiva de cada Sprint |

### Cómo se da seguimiento

- Los riesgos críticos y altos se crean como tarjetas con la etiqueta `riesgo` en el tablero de GitHub Projects.
- El eduScrum Master revisa la matriz en cada reunión de seguimiento y actualiza probabilidad e impacto con los datos reales.
- Cuando un disparador se cumple, el responsable ejecuta el plan de contingencia y lo registra en la tarjeta.
- Los riesgos que ocurren se anotan como defectos o impedimentos y alimentan el CoQ del siguiente Sprint.

---

## 6. Conclusión

Los riesgos más importantes de Open Hub Tec son el guardado sin conexión (T1), la sobrecarga del equipo (S4), la curva de aprendizaje de blockchain (T3) y el acceso a las artesanas para validar (S1). Los tres primeros se controlan con un prototipo temprano, priorización del backlog y trabajo en pareja. El financiero (F1) no frena el curso, porque el gasto en efectivo es de $0, pero sí afecta la sostenibilidad después de diciembre. Por eso el Stellar Community Fund y Drips Protocol se tratan como oportunidades por confirmar y no como recursos asegurados. La matriz se va a actualizar en cada Sprint con las horas reales, los defectos registrados y la retroalimentación de las artesanas.
