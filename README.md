# Reingeniería de Proceso con IA  
## Gestión de Incidencias IT (ITSM)

---

## Índice

- [1. Introducción](#1-introducción)
- [2. AS-IS (Proceso actual)](#2-as-is-proceso-actual)
- [3. TO-BE (Proceso rediseñado)](#3-to-be-proceso-rediseñado)
- [4. Métricas](#4-métricas)
- [5. Gobernanza](#5-gobernanza)
  - [RACI](#raci)
  - [RAID](#raid)
- [6. AI Log](#6-ai-log)

---

## 1. Introducción

El proceso seleccionado es la **gestión de incidencias IT**, un proceso clave dentro de los servicios de soporte tecnológico de una organización.

Este proceso presenta un alto volumen de solicitudes y varios problemas operativos, como errores en la clasificación de incidencias, tiempos de espera elevados y variabilidad en la resolución de los tickets.

El objetivo de este trabajo es **analizar el proceso actual (AS-IS)** e **identificar mejoras mediante el rediseño del proceso (TO-BE)** incorporando inteligencia artificial, controles de gobernanza y métricas operativas.

---

## 2. AS-IS (Proceso actual)

El modelo AS-IS describe cómo se ejecuta actualmente el proceso de gestión de incidencias.

| Paso | Dolor | Evidencia |
|-----|-----|-----|
| Recibir ticket | Variabilidad | Las incidencias llegan por múltiples canales como email, portal o chat |
| Revisar información | Retrabajo | Muchos tickets llegan con información incompleta |
| Clasificar incidencia | Error | Tickets mal categorizados o asignados |
| Asignar a equipo | Error | Las incidencias se reenvían entre equipos varias veces |
| Resolver problema | Espera | Existen colas de tickets pendientes |
| Cerrar ticket | Calidad inconsistente | El cierre se documenta de forma distinta según el agente |

Este análisis muestra varios problemas operativos, especialmente en la **clasificación inicial de incidencias y en los tiempos de resolución**.

---

## 3. TO-BE (Proceso rediseñado)

El proceso TO-BE introduce automatización mediante IA, junto con controles que permiten operar el sistema de forma segura y trazable.

| Paso | Componente | IA | Control |
|-----|-----|-----|-----|
| Recibir ticket | Portal de soporte | — | — |
| Validar campos | Reglas de negocio | — | Validación automática |
| Minimizar datos sensibles | Filtro PII | — | Minimización de datos |
| Clasificar incidencia | Servicio IA | Clasificación automática | — |
| Consultar base de conocimiento | Sistema RAG | Búsqueda en documentación interna | — |
| Generar propuesta de solución | Servicio IA | Recomendación de solución | — |
| Revisar solución | Agente humano | — | HITL (Human in the Loop) |
| Auditar y cerrar ticket | Sistema de logs | — | Auditoría |

Este rediseño permite:

- mejorar la clasificación inicial de incidencias
- reducir tiempos de resolución
- mantener control humano en decisiones críticas
- garantizar trazabilidad mediante auditoría.

---

## 4. Métricas

Para evaluar el funcionamiento del sistema se definen tres métricas clave.

| Tipo | Métrica |
|-----|-----|
| Valor | Porcentaje de incidencias resueltas en el primer contacto |
| Coste | Tiempo promedio de resolución por ticket |
| Riesgo | Número de incidencias mal clasificadas |

Estas métricas permiten evaluar **resultado del servicio, eficiencia operativa y riesgos del sistema**.

---

## 5. Gobernanza

### RACI

La matriz RACI define responsabilidades dentro del sistema.

| Actividad | Owner | SRE | Data/Legal | Negocio |
|-----|-----|-----|-----|-----|
| Diseñar proceso TO-BE | A | R | C | I |
| Operar sistema | A | R | I | I |
| Política de datos (PII) | A | C | R | I |
| Auditoría y logs | A | R | C | I |

**R** Responsible  
**A** Accountable  
**C** Consulted  
**I** Informed

---

### RAID

El análisis RAID permite anticipar problemas potenciales en la operación del sistema.

| Tipo | Descripción | Mitigación |
|-----|-----|-----|
| Risk | La IA clasifica incorrectamente incidencias críticas | Revisión humana obligatoria para incidencias prioritarias |
| Assumption | La base de conocimiento se mantiene actualizada | Revisión periódica del contenido |
| Issue | Latencia elevada en momentos de alta carga | Optimización del modelo y colas priorizadas |
| Dependency | Dependencia de un servicio externo de IA | Monitorización del servicio y acuerdos de disponibilidad |

---

## 6. AI Log

| Campo | Contenido |
|-----|-----|
| Herramienta / modelo | ChatGPT |
| Objetivo del prompt | Generar propuesta de proceso AS-IS y rediseño TO-BE para gestión de incidencias ITSM |
| Prompt utilizado | Proponer pasos de proceso, métricas operativas y controles de gobernanza para un sistema de gestión de incidencias con IA |
| Resultado generado | Se obtuvo una propuesta de proceso AS-IS y un rediseño TO-BE con clasificación automática, búsqueda en base de conocimiento y revisión humana |
| Cambios realizados | Se simplificaron algunos pasos y se ajustaron las métricas para adaptarlas al contexto del ejercicio |
| Verificación | Se comprobó que el diseño incluye métricas, controles de gobernanza y roles definidos |
