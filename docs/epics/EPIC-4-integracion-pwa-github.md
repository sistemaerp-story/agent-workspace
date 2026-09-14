# EPIC-4 — Integración con PWA Story y GitHub

**Objetivo:** que el workspace se alimente del trabajo real del producto y a su vez alimente a PWA Story, GitHub Projects y los canales de comunicación del equipo.

**Issue padre:** `sistemaerp-story/agent-workspace#4`  
**Estado:** planificado.  
**Áreas afectadas:** PWA Story, GitHub, Odoo, Supabase, Telegram/email.

---

## Contexto

Hoy el trabajo de los agentes y el trabajo del producto viven en silos parciales: los agentes generan artefactos locales y documentos en Drive/GitHub, pero no hay un flujo bidireccional entre workspace de agentes, issues de GitHub y estado de la PWA.

---

## JTBD relacionados

- **JTBD-4** Visibilidad humana del trabajo de agentes.
- **JTBD-5** Sincronización canónica de skills y reglas.

---

## Preguntas clave que resuelve este EPIC

13. ¿A qué volumen de documentos/handoffs/decisiones pasa de repo Markdown a una base de datos + UI web?
14. ¿Qué métricas nos dirán que estamos listos para construir Mission Control?
15. ¿Qué parte del workspace puede ser pública (documentación) vs. privada (decisiones internas, credenciales)?
16. ¿Qué información nunca debe escribir un agente en el workspace sin aprobación humana?
17. ¿Cómo se redactan credenciales, API keys y datos sensibles en documentos compartidos?
18. ¿Quién tiene acceso de lectura/escritura al workspace en cada etapa?

---

## Sub-issues / tareas

| # | Tarea | Descripción | Criterios de aceptación | Estado |
|---|---|---|---|---|
| 1 | Mapear issues/epics de PWA-Story | Crear entradas en `projects/` para issues y épicas relevantes de `sistemaerp-story/PWA-Story`. | Cada epic/issue priorizado tiene ficha en `projects/`. | ⏳ Pendiente |
| 2 | Sincronizar estado de spikes | Mantener alineado el estado de spikes funcionales (Idswyft, futuros) entre handoffs del workspace y GitHub issues. | Actualización de handoff reflejada en issue en < 1 día. | ⏳ Pendiente |
| 3 | Notificaciones a canales | Automatizar o estandarizar notificación de nuevos handoffs y decisiones críticas a Telegram/email. | Humanos relevantes notificados sin spam. | ⏳ Pendiente |
| 4 | Criterios de cierre de handoff | Definir cuándo un handoff se considera entregado y cuándo se puede cerrar. | Checklist de cierre documentado y aplicado. | ⏳ Pendiente |

---

## Artefactos esperados

- Fichas de proyecto en `projects/` para PWA-Story y otros repos clave.
- Workflow de sincronización handoff ↔ GitHub issue.
- Política de notificaciones.
- Checklist de cierre de handoff.

---

## Riesgos

- Sobre-notificar y generar fatiga.
- Que la sincronización manual se rompa cuando el volumen crezca.
- Publicar información sensible en canales equivocados.

---

## Próximos pasos

1. Crear ficha de proyecto para PWA-Story en `projects/`.
2. Vincular handoff de Idswyft con PWA-Story#223.
3. Definir canales y frecuencia de notificaciones.

---

## Relaciones

- **Issue padre:** `agent-workspace#4`
- **Issues hijos:** #15, #16, #17 en `agent-workspace`.
- **Depende de:** EPIC-2 y EPIC-3.
- **Bloquea:** EPIC-5 en parte (Mission Control necesita datos estructurados).
- **Relacionado con:** PWA-Story#223, `EVOLUTION_PLAN.md`, Telegram.
