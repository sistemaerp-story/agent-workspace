# EPIC-2 — Handoffs y decision records funcionales

**Objetivo:** que cualquier agente del ecosistema StoryWeProduce pueda dejar y consumir handoffs y decisiones en el workspace de forma consistente.

**Issue padre:** `sistemaerp-story/agent-workspace#2`  
**Estado:** planificado / en definición.  
**Áreas afectadas:** comunicación entre agentes, continuidad de sesiones, gobernanza de decisiones.

---

## Contexto

Hoy los handoffs ocurren de forma informal: resúmenes al final de sesión, memoria comprimida, mensajes en Telegram. Cuando un agente distinto retoma el trabajo, pierde contexto o lo reconstruye de forma incompleta. Necesitamos un formato estándar que funcione para Hermes, OpenClaw, Kimi y futuros agentes.

---

## JTBD relacionados

- **JTBD-2** Handoff limpio entre agentes.
- **JTBD-3** Conocimiento reutilizable.
- **JTBD-4** Visibilidad humana del trabajo de agentes.

---

## Preguntas clave que resuelve este EPIC

5. ¿Quién (o qué) decide qué entra al workspace: un humano, un agente coordinador, o ambos?
6. ¿Cómo se versionan las decisiones y los skills para que no se revirtan por error?
7. ¿Qué pasa cuando dos agentes editan el mismo documento al mismo tiempo?
8. ¿Cómo se resuelve un conflicto entre lo que dice el workspace y la memoria local de un agente?

---

## Sub-issues / tareas

| # | Tarea | Descripción | Criterios de aceptación | Estado |
|---|---|---|---|---|
| 1 | Schema de handoff | Especificar campos obligatorios, opcionales y metadatos de un handoff. | Documento de schema aprobado y template actualizado. | ⏳ Pendiente |
| 2 | Schema de decision record | Especificar formato de decision record (contexto, opciones, decisión, consecuencias). | Documento de schema aprobado y template actualizado. | ⏳ Pendiente |
| 3 | Validación cruzada de agents | Validar que Hermes, OpenClaw y Kimi puedan leer y escribir handoffs con el mismo template sin pérdida de contexto. | Prueba de handoff round-trip exitosa con los 3 agents. | ⏳ Pendiente |
| 4 | Primer handoff real | Crear handoff funcional del spike de Idswyft al siguiente agente de integración. | Handoff mergeado, issue vinculado, receptor lo consume sin preguntas. | ✅ Hecho (en `handoffs/idswyft-spike-2026-09-11.md`) |
| 5 | Primer decision record | Crear decision record de la política de no auto-instalar herramientas evaluadas. | DR mergeado y referenciado por evaluaciones de TOOLCHAIN. | ✅ Hecho (en `constraints/no-auto-install.md`, pendiente convertir a DR formal) |

---

## Artefactos esperados

- Schema de handoff documentado.
- Schema de decision record documentado.
- Templates estables y validados por 3 agents.
- Al menos 2 handoffs reales y 2 decision records.

---

## Riesgos

- Diferentes agents interpretan Markdown de forma distinta.
- Un agente sobreescribe un handoff antes de que otro lo lea.
- Los humanos no revisan handoffs críticos a tiempo.

---

## Próximos pasos

1. Aprobar schema de handoff y decision record.
2. Realizar prueba round-trip Hermes → OpenClaw → Kimi.
3. Convertir `constraints/no-auto-install.md` en decision record formal.

---

## Relaciones

- **Issue padre:** `agent-workspace#2`
- **Issues hijos:** #9, #10, #11 en `agent-workspace`.
- **Depende de:** EPIC-1 (estructura y templates base).
- **Bloquea:** EPIC-4 (notificaciones y cierre de handoffs).
- **Relacionado con:** PWA-Story#223 (Idswyft), `constraints/no-auto-install.md`.
