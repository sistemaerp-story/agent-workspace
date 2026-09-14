# Story Agent Workspace

Workspace compartido para los agentes de StoryWeProduce (Hermes, OpenClaw, Kimi y futuros).

Propósito: centralizar contexto, handoffs, decisiones, skills, constraints y conocimiento reutilizable del ecosistema de agentes.

---

## Estructura

| Carpeta | Qué vive aquí | Ejemplo |
|---|---|---|
| `projects/` | Contexto por proyecto o user story de la PWA. | `PWA-Story.md`, `Odoo-Integration.md` |
| `constraints/` | Reglas duras que todos los agentes deben respetar. | `no-auto-install.md`, `data-redaction.md` |
| `skills/` | Skills activas del ecosistema en formato Markdown. | `odoo-general-ledger-report.md` |
| `handoffs/` | Handoffs entre agentes o entre sesiones. | `idswyft-spike-2026-09-13.md` |
| `decisions/` | Decision records (DR). | `DR-001-no-auto-install-tools.md` |
| `references/` | Artículos, metodologías y recursos externos relevantes. | `marketing-engineer-shannholmberg.md` |
| `templates/` | Plantillas para handoffs, decisiones y lecciones. | `handoff-template.md` |
| `scripts/` | Utilidades para sincronizar, validar o refrescar el workspace. | `sync-skills.py` |

---

## Convenciones

- Todo documento debe tener fecha, autor y propósito en el encabezado.
- Los handoffs usan el template en `templates/handoff-template.md`.
- Las decisiones usan el formato ADR en `templates/decision-template.md`.
- No escribir credenciales; usar `[REDACTED]`.
- Cada cambio significativo debe reflejarse en el changelog del proyecto correspondiente.

---

## Flujo de contribución

1. Un agente termina trabajo significativo → escribe/actualiza handoff en `handoffs/`.
2. Una decisión de negocio o arquitectura relevante → decision record en `decisions/`.
3. Una lección reutilizable → skill o constraint actualizado en `skills/`/`constraints/`.
4. Referencia externa valiosa → resumen en `references/`.
5. Humanos y agentes coordinadores revisan periódicamente `handoffs/` y `decisions/`.

---

## Integración con el ecosistema

- GitHub: issues de `PWA-Story` y otros repos se vinculan a entradas del workspace.
- PWA Story: proyectos, épicas y entregas se documentan en `projects/`.
- Odoo / Supabase / Google Workspace: datos relevantes se resumen en `projects/` como contexto de negocio.
- Telegram / email: notificaciones de nuevos handoffs y decisiones críticas.

---

## Estado

- 2026-09-13: repo creado, estructura inicial y README operativo.

---

## JTBD y diseño completo

Ver `docs/AGENT_WORKSPACE_DESIGN.md` (o link a diseño en PWA-Story cuando se sincronice).
