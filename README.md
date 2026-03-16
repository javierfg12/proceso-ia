# Reingeniería de proceso con IA

## 1. Proceso elegido

(Explicación breve)

---

## 2. AS-IS (proceso actual)

| Paso | Dolor | Evidencia |
|----|----|----|
| Recibir ticket | Variabilidad | Tickets llegan por email, portal y chat |
| Revisar información | Retrabajo | Faltan datos en muchos tickets |
| Clasificar incidencia | Error | Tickets mal clasificados |
| Asignar equipo | Error | Tickets se reenvían varias veces |
| Resolver problema | Espera | Hay colas de incidencias pendientes |
| Cerrar ticket | Calidad inconsistente | Cada agente documenta el cierre de forma distinta |

---

## 3. TO-BE (proceso rediseñado)

| Paso | Componente | IA | Control |
|----|----|----|----|
| Recibir ticket | Portal de soporte | — | — |
| Validar campos | Reglas de negocio | — | — |
| Minimizar datos sensibles | Filtro PII | — | Minimización de datos |
| Clasificar incidencia | Servicio IA | Clasificación | — |
| Consultar base conocimiento | RAG | Búsqueda | — |
| Generar propuesta de solución | Servicio IA | Recomendación | — |
| Revisar solución | Agente humano | — | HITL |
| Auditar y cerrar ticket | Sistema de logs | — | Auditoría |
---

## 4. Métricas

| Tipo | Métrica |
|---|---|
| Valor | % de incidencias resueltas en primer contacto |
| Coste | Tiempo promedio de resolución por ticket |
| Riesgo | Número de incidencias mal clasificadas |
---

## 5. Gobernanza

### RACI

| Actividad | Owner | SRE | Data/Legal | Negocio |
|---|---|---|---|---|
| Diseñar proceso TO-BE | A | R | C | I |
| Operar sistema | A | R | I | I |
| Política de datos (PII) | A | C | R | I |
| Auditoría y logs | A | R | C | I |

### RAID

| Tipo | Descripción | Mitigación |
|---|---|---|
| Risk | La IA clasifica incorrectamente incidencias críticas | HITL obligatorio para incidencias P1/P2 |
| Assumption | La base de conocimiento está actualizada | Revisión mensual del contenido |
| Issue | Alta latencia en momentos de alta carga | Optimización del modelo y cola priorizada |
| Dependency | Dependencia de API externa de IA | Contrato de servicio y monitorización |

---

## 6. AI Log

| Campo | Contenido |
|---|---|
| Herramienta / modelo | ChatGPT |
| Objetivo del prompt | Generar propuesta de proceso AS-IS y rediseño TO-BE para gestión de incidencias ITSM |
| Prompt utilizado | "Propón un proceso AS-IS y TO-BE para gestión de incidencias ITSM incluyendo pasos, palancas de IA, controles y métricas." |
| Resultado generado | Se propuso un flujo AS-IS de 6 pasos y un TO-BE de 8 pasos con clasificación automática, búsqueda en base de conocimiento y revisión humana |
| Cambios realizados | Se ajustaron los pasos para adaptarlos al contexto ITSM y se simplificaron las métricas |
| Verificación | Se revisó coherencia del pipeline, controles de gobernanza y correspondencia con los requisitos del curso |
