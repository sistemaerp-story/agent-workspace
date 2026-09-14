# No auto-instalar herramientas evaluadas

**Estado:** activo  
**Fecha:** 2026-09-10  
**Áreas afectadas:** evaluación de herramientas, spikes, infraestructura.

---

## Regla

Ninguna herramienta candidata se instala automáticamente en la infraestructura de StoryWeProduce solo porque apareció en una evaluación, búsqueda o recomendación.

La instalación requiere **explícita aprobación del humano responsable** (Jorge) después de:
- Evaluación de capa duplicada.
- Análisis de riesgos legales, de seguridad, de licencia y de infraestructura.
- Definición de user story o spike claro.
- Registro en `TOOLCHAIN_Y_SKILLS.md §2.3`.

---

## Por qué

- Evitar acumulación de servicios no usados que consumen recursos y aumentan superficie de ataque.
- Mantener el stack deliberado y alineado con el negocio.
- Respetar la preferencia de Jorge: "Evaluaciones de tools nuevas van a TOOLCHAIN_Y_SKILLS.md §2.3 con análisis de capa duplicada, nunca auto-instalar."

---

## Excepciones

- Spikes previamente autorizados (ej. Idswyft Community para verificación de identidad).
- Herramientas cuya instalación sea reversible y aislada en contenedor, y que el usuario haya pedido explícitamente.

---

## Relaciones

- Relacionado con: `AGENT_WORKSPACE_DESIGN.md` EPIC-2 y EPIC-3.
- Referenciado por: evaluaciones registradas en `TOOLCHAIN_Y_SKILLS.md`.
