---
name: progress-tracker
description: Use when updating PROGRESS.md with weekly entries, updating certification status, or recording study hours. Never overwrites existing entries.
---

# Progress Tracker Skill

## Regla principal

**NUNCA sobreescribir entradas existentes en PROGRESS.md.**

Solo agregar contenido al final del archivo, después de la última semana registrada.

## Cómo actualizar el estado de certificaciones

En la tabla de "Resumen general", solo actualizar la columna "Estado" y "Fecha real":

```markdown
| CKA | ✅ Aprobado | Mes 9 | 2027-03-15 |
```

Estados válidos únicamente:
- `⏳ Pendiente`
- `🔄 En curso`
- `✅ Aprobado`
- `❌ Reprogramado`

## Cómo agregar una nueva semana

1. Identificar el número de la última semana registrada
2. Agregar la nueva semana con el número consecutivo correcto
3. No modificar semanas anteriores bajo ninguna circunstancia

Formato exacto a usar (no modificar la estructura):

```markdown
---

### Semana XX — [fecha inicio] al [fecha fin]

**Fase actual:** Fase X — Nombre de la fase
**Certificación en curso:** Nombre de la cert

#### Horas de estudio
- Objetivo: Xh
- Real: Xh

#### Objetivos de la semana
- [ ] Objetivo 1
- [ ] Objetivo 2

#### Laboratorios realizados
- Lab X: descripción breve del laboratorio completado

#### Problemas encontrados
- [Problema encontrado] → [Solución aplicada o pendiente]

#### Lecciones aprendidas
- Lección concreta aprendida esta semana

#### Estado general
[ ] En tiempo  [ ] Adelantado  [ ] Atrasado — motivo: ___
```

## Cómo actualizar la tabla de horas acumuladas

Solo actualizar la celda "Horas reales" del mes correspondiente.
Calcular Delta = Horas objetivo - Horas reales (positivo = adelantado, negativo = atrasado).

## Cuándo NO usar este skill

- Para crear un PROGRESS.md desde cero (usar el template del ROADMAP.md)
- Para modificar el formato de la tabla de certificaciones
- Para cambiar los objetivos de horas por mes (esos son fijos del programa)
