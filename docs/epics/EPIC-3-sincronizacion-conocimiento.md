# EPIC-3 — Sincronización de conocimiento

**Objetivo:** convertir lecciones, evaluaciones de herramientas y diagramas del proyecto en conocimiento reutilizable y accesible para todos los agentes.

**Issue padre:** `sistemaerp-story/agent-workspace#3`  
**Estado:** planificado.  
**Áreas afectadas:** knowledge management, skills, constraints, referencias, arquitectura.

---

## Contexto

StoryWeProduce genera constante conocimiento: evaluaciones de herramientas en `TOOLCHAIN_Y_SKILLS.md`, diagramas del repo PWA, handoffs de spikes, lecciones de errores. Sin un workflow de promoción, ese conocimiento queda atrapado en sesiones individuales o documentos que nadie referencia.

---

## JTBD relacionados

- **JTBD-3** Conocimiento reutilizable.
- **JTBD-5** Sincronización canónica de skills y reglas.

---

## Preguntas clave que resuelve este EPIC

9. ¿Cómo se conecta el workspace con la PWA Story (proyectos, épicas, issues, entregas)?
10. ¿Qué datos deben fluir desde Odoo/Supabase/Google Drive hacia el workspace?
11. ¿Qué datos del workspace deben reflejarse de vuelta en `EVOLUTION_PLAN.md` o GitHub Projects?
12. ¿Cómo se notifica a los humanos cuando un agente publica un handoff o una decisión?

---

## Sub-issues / tareas

| # | Tarea | Descripción | Criterios de aceptación | Estado |
|---|---|---|---|---|
| 1 | Workflow TOOLCHAIN → skill/constraint | Definir cómo una evaluación de TOOLCHAIN se promueve a skill o constraint del workspace. | Workflow documentado y aplicado a 2 casos reales. | ⏳ Pendiente |
| 2 | Mover referencias clave | Migrar resúmenes de recursos externos (marketing engineer, graph engineering, etc.) al workspace. | Referencias en `references/` con formato estándar. | ✅ Parcial (2 referencias ya creadas) |
| 3 | Linkear EVOLUTION_PLAN.md | Establecer vínculos automáticos o manuales entre `EVOLUTION_PLAN.md` y handoffs/decisiones. | Cada ítem de EVOLUTION_PLAN apunta a handoff/DR cuando aplique. | ⏳ Pendiente |
| 4 | Revisión de archivos huérfanos | Implementar revisión periódica basada en metodología de graph engineering para detectar documentos no referenciados. | Primera revisión realizada y reporte de huérfanos publicado. | ⏳ Pendiente |

---

## Artefactos esperados

- Workflow documentado para promover evaluaciones a skills/constraints.
- `references/` poblado con recursos clave del proyecto.
- `EVOLUTION_PLAN.md` vinculado a handoffs y decisiones.
- Proceso periódico de limpieza de archivos huérfanos.

---

## Riesgos

- El proceso de promoción se vuelve burocrático y los agentes lo evitan.
- Las referencias se desactualizan.
- La revisión de huérfanos genera trabajo de mantenimiento sin priorizar valor.

---

## Próximos pasos

1. Definir criterios de promoción TOOLCHAIN → skill/constraint.
2. Completar migración de referencias pendientes.
3. Aplicar primera revisión de archivos huérfanos en el workspace.

---

## Relaciones

- **Issue padre:** `agent-workspace#3`
- **Issues hijos:** #12, #13, #14 en `agent-workspace`.
- **Depende de:** EPIC-1 y EPIC-2.
- **Bloquea:** EPIC-4 (integración con PWA Story).
- **Relacionado con:** `TOOLCHAIN_Y_SKILLS.md`, `EVOLUTION_PLAN.md`, `references/graph-engineering-charliehills.md`.
