# EPIC-1 — Fundamentos del agent-workspace repo

**Objetivo:** crear el repo `sistemaerp-story/agent-workspace` con estructura, convenciones y README operativo.

**Issue padre:** — este es el epic raíz.  
**Estado:** en progreso / parcialmente completado.  
**Áreas afectadas:** infraestructura del ecosistema de agentes, conocimiento compartido, flujo de trabajo de agentes.

---

## Contexto

StoryWeProduce opera con múltiples agentes (Hermes, OpenClaw, Kimi y futuros) en sesiones independientes. La memoria y el contexto viven dispersos: skills locales, memoria de Hermes, handoffs informales, documentos en Drive y notas de sesión. Necesitamos un single source of truth que cualquier agente pueda leer y escribir.

---

## JTBD relacionados

- **JTBD-1** Contexto actualizado entre sesiones.
- **JTBD-5** Sincronización canónica de skills y reglas.

---

## Preguntas clave que resuelve este EPIC

1. ¿Qué información debe vivir en el workspace vs. en skills/memory locales?
2. ¿Cómo se nombra y organiza el conocimiento para que un agente lo encuentre?
3. ¿Qué formato debe tener un handoff para ser consumido por Hermes, OpenClaw y Kimi?
4. ¿Cómo se mantiene la estructura sin que se llene de archivos huérfanos?

---

## Sub-issues / tareas

| # | Tarea | Descripción | Criterios de aceptación | Estado |
|---|---|---|---|---|
| 1 | Crear repo y permisos | Crear `sistemaerp-story/agent-workspace`, público, con branch protection y acceso del equipo. | Repo accesible, main protegida, CI básico configurado. | ✅ Hecho |
| 2 | Estructura de carpetas | Definir y documentar `projects/`, `skills/`, `constraints/`, `handoffs/`, `decisions/`, `references/`, `templates/`, `scripts/`. | Carpetas creadas, README describe cada una con ejemplo. | ✅ Hecho |
| 3 | README operativo | Escribir README con propósito, JTBD, convenciones de nombres, flujo de contribución y formato de handoff. | README mergeado en main. | ✅ Hecho |
| 4 | Templates base | Crear templates de handoff, decision record y lesson learned. | 3 templates mergeados y probados. | ✅ Hecho |
| 5 | Migrar skills/constraints críticas | Migrar de Hermes skills/constraints clave como single source of truth inicial. | Al menos 2 constraints y 2 skills migrados y funcionales. | ⏳ Pendiente |
| 6 | Carpetas de negocio y proyectos | Crear carpetas adicionales para comprender el negocio: `business/`, `projects/`, `clients/`, `vendors/`, `talent/` con mapas de dominio. | Estructura de negocio documentada y validada por Jorge. | ⏳ Pendiente |

---

## Artefactos esperados

- Repo `sistemaerp-story/agent-workspace` operativo.
- README.md con propósito y convenciones.
- Estructura de carpetas inicial poblada.
- Templates de handoff, decision y lesson learned.
- Constraints `no-auto-install.md` y `data-redaction.md`.

---



### Preguntas clave adicionales del comentario de Jorge
- ¿Qué carpetas adicionales necesitamos para modelar el negocio de StoryWeProduce (proyectos, clientes, proveedores, talento, producción)?
- ¿Cómo garantizamos que todos los agentes (Hermes, OpenClaw, Kimi) compartan información sin duplicarla?
- ¿Qué información va a GitHub (texto, código, decisiones) y qué va a Drive (archivos grandes, assets, videos)?
- ¿Cómo detectamos y eliminamos documentos huérfanos de forma periódica?
- ¿Qué significa "higiene extrema" en worktrees y directorios del workspace?

### Decisiones derivadas del comentario
- Agregar carpetas de negocio al workspace, no solo técnicas.
- Definir política de almacenamiento dual: GitHub para texto/estructura, Drive para archivos grandes.
- Implementar revisión periódica de huérfanos y worktrees limpios.

## Riesgos

- Que el repo se convierta en un cajón de sastre si no hay revisión periódica.
- Que los agentes no adopten los templates sin validación cruzada.
- Que las skills migradas queden desactualizadas respecto a las locales de Hermes.

---

## Próximos pasos

1. Completar migración de skills/constraints críticas (sub-issue #8 del repo agent-workspace).
2. Validar que OpenClaw y Kimi puedan leer y escribir usando los templates.
3. Establecer revisión periódica de archivos huérfanos.

---

## Relaciones

- **Issues hijos:** #6, #7, #8 en `agent-workspace`.
- **Depende de:** aprobación del diseño en `docs/AGENT_WORKSPACE_DESIGN.md`.
- **Bloquea:** EPIC-2, EPIC-3 y EPIC-4.
- **Relacionado con:** PWA-Story#223 (handoff de Idswyft ya incluido en el workspace).
