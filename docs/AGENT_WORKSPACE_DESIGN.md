# Story Agent Workspace — Diseño de proyecto

## Propósito
Crear un **workspace compartido para los agentes de StoryWeProduce** (Hermes, OpenClaw, Kimi y futuros) donde puedan leer, escribir y sincronizar: contexto de proyecto, conocimiento compartido, decisiones, tareas, handoffs y resultados. Empezar por una estructura de carpetas/repo (`agent-workspace`) y evolucionar hacia una plataforma web/Mission Control cuando el volumen y el equipo lo justifiquen.

---

## Jobs-to-be-Done (JTBD)

### JTBD-1 — Contexto actualizado entre sesiones
*Cuando un agente retoma un proyecto, necesita saber qué se acordó, qué está pendiente y qué no debe repetir, para no perder tiempo ni contradecir decisiones.*

**Indicadores de éxito:**
- 80% de las preguntas de contexto resueltas leyendo el workspace, sin consultar a humanos.
- Ninguna decisión o restricción se pierde entre sesiones de agentes distintos.

### JTBD-2 — Handoff limpio entre agentes
*Cuando Hermes termina una tarea y OpenClaw/Kimi la continúa, el segundo agente debe entender el estado, los artefactos y los criterios de aceptación, para continuar sin reprocesos.*

**Indicadores de éxito:**
- Un handoff puede ser consumido por cualquier agente del ecosistema sin preguntas de aclaración.
- El tiempo de ramp-up de un agente secundario es < 5 minutos de lectura.

### JTBD-3 — Conocimiento reutilizable
*Cuando un agente resuelve un problema o aprende una lección, esa información debe quedar disponible para futuras tareas similares, para no redescubrir la misma solución.*

**Indicadores de éxito:**
- Cada lección aprendida se vincula a al menos un skill, constraint o documento de referencia.
- Reducción de consultas repetidas sobre el mismo tema en un 50% tras 3 meses.

### JTBD-4 — Visibilidad humana del trabajo de agentes
*Cuando Jorge o un humano del equipo quiere saber qué hicieron los agentes, debe poder verlo en un dashboard sin revisar logs de chat.*

**Indicadores de éxito:**
- Estado de tareas, decisiones y handoffs consultable en < 2 clics.
- Historial de cambios en el workspace trazable por agente, sesión y fecha.

### JTBD-5 — Sincronización canonica de skills y reglas
*Cuando el equipo actualiza un skill o una regla, todos los agentes deben usar la misma versión, para evitar inconsistencias entre runtimes.*

**Indicadores de éxito:**
- Single source of truth para skills activas, constraints y prompts operativos.
- Cualquier agente puede refrescar su contexto desde el workspace en menos de 1 minuto.

---

## Preguntas clave para que funcione

### Diseño y estructura
1. ¿Qué información debe vivir en el workspace y qué debe seguir en skills/memory de cada agente?
2. ¿Cómo se nombra y organiza el conocimiento para que un agente lo encuentre sin recordar rutas exactas?
3. ¿Qué formato debe tener un handoff para ser consumido por Hermes, OpenClaw y Kimi por igual?
4. ¿Cómo se mantiene la estructura sin que se convierta en un basurero de archivos huérfanos?

### Sincronización y gobernanza
5. ¿Quién (o qué) decide qué entra al workspace: un humano, un agente coordinador, o ambos?
6. ¿Cómo se versionan las decisiones y los skills para que no se revirtan por error?
7. ¿Qué pasa cuando dos agentes editan el mismo documento al mismo tiempo?
8. ¿Cómo se resuelve un conflicto entre lo que dice el workspace y la memoria local de un agente?

### Integración con el ecosistema
9. ¿Cómo se conecta el workspace con la PWA Story (proyectos, épicas, issues, entregas)?
10. ¿Qué datos deben fluir desde Odoo/Supabase/Google Drive hacia el workspace?
11. ¿Qué datos del workspace deben reflejarse de vuelta en EVOLUTION_PLAN.md o GitHub Projects?
12. ¿Cómo se notifica a los humanos cuando un agente publica un handoff o una decisión?

### Escalabilidad
13. ¿A qué volumen de documentos/handoffs/decisiones pasa de repo Markdown a una base de datos + UI web?
14. ¿Qué métricas nos dirán que estamos listos para construir Mission Control?
15. ¿Qué parte del workspace puede ser pública (documentación) vs. privada (decisiones internas, credenciales)?

### Seguridad y permisos
16. ¿Qué información nunca debe escribir un agente en el workspace sin aprobación humana?
17. ¿Cómo se redactan credenciales, API keys y datos sensibles en documentos compartidos?
18. ¿Quién tiene acceso de lectura/escritura al workspace en cada etapa?

---

## Épicas y sub-issues propuestos

### EPIC-1 — Fundamentos del agent-workspace repo
**Objetivo:** crear el repo `sistemaerp-story/agent-workspace` con estructura, convenciones y README operativo.

**Sub-issues:**
- #1 Crear repo `sistemaerp-story/agent-workspace` y configurar permisos/branch protection.
- #2 Definir y documentar estructura de carpetas (`projects/`, `skills/`, `constraints/`, `handoffs/`, `decisions/`, `references/`, `templates/`).
- #3 Escribir README con propósito, JTBD, convenciones de nombres, flujo de contribución y formato de handoff.
- #4 Crear templates de handoff, decision record y lección aprendida.
- #5 Migrar skills/constraints críticas de Hermes al workspace como single source of truth.

### EPIC-2 — Handoffs y decision records funcionales
**Objetivo:** que cualquier agente pueda dejar y consumir handoffs y decisiones en el workspace.

**Sub-issues:**
- #6 Especificar schema de handoff (estado, artefactos, criterios de aceptación, próximos pasos, riesgos).
- #7 Especificar schema de decision record (contexto, opciones, decisión, consecuencias, fecha, owner).
- #8 Validar que Hermes, OpenClaw y Kimi puedan leer y escribir handoffs con el mismo template.
- #9 Crear primer handoff real: Idswyft spike → siguiente agente de integración.
- #10 Crear primer decision record: política de no auto-instalar herramientas evaluadas.

### EPIC-3 — Sincronización de conocimiento
**Objetivo:** convertir lecciones, evaluaciones y diagramas del proyecto en conocimiento reutilizable.

**Sub-issues:**
- #11 Definir workflow para promover una evaluación de TOOLCHAIN a skill/constraint del workspace.
- #12 Mover referencias clave (marketing engineer, graph engineering, etc.) al workspace.
- #13 Linkear automáticamente EVOLUTION_PLAN.md con handoffs y decision records.
- #14 Establecer revisión periódica de archivos huérfanos (basado en graph engineering).

### EPIC-4 — Integración con PWA Story y GitHub
**Objetivo:** que el workspace se alimente de y alimente al trabajo real del producto.

**Sub-issues:**
- #15 Mapear issues/epics de PWA-Story a entradas del workspace.
- #16 Sincronizar estado de spikes funcionales (Idswyft, futuros) entre handoffs y GitHub issues.
- #17 Automatizar notificación de nuevos handoffs/decisiones a canales relevantes (Telegram/email).
- #18 Definir criterios de aceptación para cerrar un handoff.

### EPIC-5 — Mission Control (fase 2)
**Objetivo:** cuando el volumen lo justifique, ofrecer una UI web para navegar el workspace.

**Sub-issues:**
- #19 Definir triggers/métricas para iniciar Mission Control.
- #20 Diseñar vistas: dashboard de handoffs, decisiones, skills, tareas activas, agentes.
- #21 Elegir stack (Next.js/FastAPI/Supabase vs. integrar en PWA Story).
- #22 Spike de UI con datos del workspace en tiempo real.

---

## Próximos pasos inmediatos
1. Revisar y aprobar este documento con Jorge.
2. Crear el repo `sistemaerp-story/agent-workspace`.
3. Crear épicas EPIC-1 a EPIC-5 como issues de GitHub.
4. Crear sub-issues #1 a #22.
5. Linkear issues existentes relevantes (p. ej. #223 Idswyft) como ejemplos de handoff.

---

## Fecha
2026-09-13

## Autor
Hermes Agent / StoryWeProduce
