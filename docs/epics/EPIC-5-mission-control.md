# EPIC-5 — Mission Control (fase 2)

**Objetivo:** cuando el volumen de handoffs, decisiones, skills y tareas lo justifique, ofrecer una UI web para navegar, buscar y actualizar el workspace de agentes de StoryWeProduce.

**Issue padre:** `sistemaerp-story/agent-workspace#5`  
**Estado:** planificado / en espera de triggers.  
**Áreas afectadas:** frontend, backend, UX, infraestructura.

---

## Contexto

Un repo Markdown es suficiente mientras el volumen de documentos sea manejable. Cuando el workspace crezca, los humanos y los propios agentes necesitarán búsqueda, filtros, estado en tiempo real y dashboards. Mission Control es la evolución natural del workspace a una plataforma web.

---

## JTBD relacionados

- **JTBD-4** Visibilidad humana del trabajo de agentes.

---

## Preguntas clave que resuelve este EPIC

13. ¿A qué volumen de documentos/handoffs/decisiones pasa de repo Markdown a una base de datos + UI web?
14. ¿Qué métricas nos dirán que estamos listos para construir Mission Control?
15. ¿Qué parte del workspace puede ser pública (documentación) vs. privada (decisiones internas, credenciales)?

---

## Sub-issues / tareas

| # | Tarea | Descripción | Criterios de aceptación | Estado |
|---|---|---|---|---|
| 1 | Triggers y métricas | Definir qué métricas activan la construcción de Mission Control. | Documento de triggers aprobado. | ⏳ Pendiente |
| 2 | Diseño de vistas | Diseñar dashboard de handoffs, decisiones, skills, tareas activas y agentes. | Mockups o especificación de UI aprobados. | ⏳ Pendiente |
| 3 | Elección de stack | Elegir entre Next.js/FastAPI/Supabase standalone o integrar en PWA Story. | ADR de stack mergeado. | ⏳ Pendiente |
| 4 | Spike de UI | Construir spike funcional con datos del workspace en tiempo real. | Demo funcional desplegada en staging. | ⏳ Pendiente |

---

## Artefactos esperados

- Documento de triggers/métricas.
- Especificación de vistas de Mission Control.
- ADR de stack.
- Spike desplegado.

---

## Riesgos

- Construir Mission Control antes de que el volumen lo justifique (sobre-ingeniería).
- Elegir un stack que duplique esfuerzo con la PWA Story.
- Exponer información sensible en una UI web.

---

## Próximos pasos

1. Recopilar métricas base del uso del workspace durante 1-2 meses.
2. Definir triggers claros (número de handoffs, decisiones, skills activas, agentes).
3. Decidir si Mission Control se integra en PWA Story o es producto independiente.

---

## Relaciones

- **Issue padre:** `agent-workspace#5`
- **Issues hijos:** #18, #19, #20 en `agent-workspace`.
- **Depende de:** EPIC-1, EPIC-2, EPIC-3 y EPIC-4.
- **Bloquea:** — es la fase final de maduración.
- **Relacionado con:** PWA Story, `pwa-design-system`, `stitch-pwa-redesign`.
