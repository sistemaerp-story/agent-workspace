# Referencia — How to Become a Marketing Engineer

- **Fuente:** Shann³ (@shannholmberg) en X (Lunar Strategy)
- **URL:** https://x.com/shannholmberg/status/2098004743536750869
- **Título:** "How to Become a Marketing Engineer"
- **Fecha de captura:** 2026-09-13
- **Propósito para StoryWeProduce:** inspiración para diseñar equipos de marketing técnico basados en agentes, workflows y conocimiento estructurado.

---

## Concepto central

Un **Marketing Engineer** combina:
- Análisis de campañas y datos.
- Creatividad.
- Código.
- Agentes de IA.

No es solo un operador de herramientas: es alguien que diseña sistemas de marketing reproducibles, donde los agentes ejecutan workflows y los humanos revisan y deciden.

---

## Componentes del sistema

| Término | Definición |
|---|---|
| **Model** | El modelo de IA elegido para una tarea (research, plan, write). |
| **Harness** | El software que rodea al modelo: acceso a archivos, herramientas, ejecución de código y control de permisos. |
| **ADE** | Agent Development Environment: interfaz donde se trabaja con agentes, revisa sus acciones y guía el trabajo. |

---

## Arquitectura del conocimiento

```
shared-knowledge/
├── audience.md
├── product-and-offer.md
└── positioning.md

vertical/
├── landing-page/
├── paid/
├── email/
├── content/
├── lifecycle/
└── outbound/

work/
├── brief.md
├── campaign-book/
├── research/
├── tickets/
└── results/
```

| Área | Qué contiene |
|---|---|
| **Shared knowledge** | Información de la empresa reutilizable: producto, audiencia, posicionamiento, brand guidelines. |
| **Vertical knowledge** | Investigación, ejemplos y guías específicas de un canal o disciplina. |
| **Work** | Campañas activas, briefs, planes y trabajo en progreso. |
| **Workflows** | Pasos y conexiones que llevan una tarea desde sus insumos hasta un output terminado. |
| **Skills, agents & code** | Instrucciones reutilizables, definiciones de agentes y scripts. |
| **Outputs** | Assets y deliverables producidos. |
| **Results & learnings** | Reportes de performance, feedback y hallazgos reutilizables. |

---

## Flujo operativo general

```
SHARED KNOWLEDGE          CAMPAIGN CONTEXT
audience + offer         brief + research
        │                       │
        └───────────┬───────────┘
                    ↓
              WORKFLOW RUN
                    ↓
             drafts + review
                    ↓
            approved deliverables
                    ↓
             campaign results
                    ↓
          findings + your feedback
                    ↓
        context for the next campaign
```

---

## Lecciones aplicables a StoryWeProduce

1. **Estructurar el conocimiento por capas:** compartido, vertical, trabajo, outputs y aprendizajes.
2. **Definir workflows como tickets estructurados** con checks, retry budget y gates de aprobación humana.
3. **Usar agentes para ejecución, no para decisión final:** el humano revisa evidencia y aprueba.
4. **Conectar datos de canales, CRM y warehouse** para alimentar briefs y tests siguientes.
5. **Documentar approved claims, objections y learnings** como inputs reutilizables para campañas.

---

## Notas

- No es software instalable: es metodología y referencia de arquitectura de trabajo.
- Útil para diseñar el equipo de marketing de StoryWeProduce con herramientas de agentes y flujos de aprobación.
- Para implementar, considerar adaptar conceptos a los workflows ya existentes en la PWA (aprobaciones, notificaciones, tickets).
