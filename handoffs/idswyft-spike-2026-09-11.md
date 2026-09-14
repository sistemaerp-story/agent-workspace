# Handoff — Idswyft Community Spike

## Metadata
- **Fecha:** 2026-09-11
- **De:** Hermes Agent
- **Para:** Orquestador / agente de integración Odoo↔Story PWA
- **Proyecto:** Verificación de identidad del firmante antes de firma en Odoo
- **Issue/PR relacionado:** [sistemaerp-story/PWA-Story#223](https://github.com/sistemaerp-story/PWA-Story/issues/223)
- **EVOLUTION_PLAN:** CONTR-11
- **Estado:** ✅ aprobado para siguiente fase

---

## Resumen ejecutivo

Idswyft Community es una plataforma open-source self-hosted de verificación de identidad (KYC). Se levantó como spike funcional en `127.0.0.1:18100`, se creó un developer, se verificó por OTP y se obtuvo una API key de producción/sandbox. El endpoint `POST /api/v2/verify/initialize` responde correctamente con `verification_id`, `session_token`, `verification_url` y estado `AWAITING_FRONT`.

---

## Estado actual

- **Funciona:** Docker Compose con 4 servicios healthy (API, engine, postgres, frontend).
- **Probado:** registro de developer, OTP, API key, inicialización de verificación con `document_only`.
- **Pendiente:** integración con flujo de firma de contratos en Odoo / Story PWA.

---

## Artefactos

| Tipo | Ubicación | Notas |
|---|---|---|
| Código/config | `/root/Sistema-AI/Vigente/idswyft-spike/` | Docker Compose, `.env`, handoff local |
| API | `http://127.0.0.1:18100` | expuesta localmente |
| Frontend portal | `http://127.0.0.1:18101` | portal de developer |
| API key | `[REDACTED]` | obtener via `/api/auth/developer/otp/*` → `/api/developer/api-key` |

---

## Decisiones tomadas

- Se promueve de evaluación a **spike funcional** por indicación de Jorge.
- Se creó issue #223 y punto CONTR-11 en `EVOLUTION_PLAN.md`.
- No se integra aún a producción; espera sprint de integración Odoo.

---

## Riesgos y bloqueos

- 31★ en GitHub — proyecto muy temprano.
- Datos biométricos sensibles: implicaciones legales/privacidad/LGPD.
- Motor de liveness/OCR puede requerir modelos adicionales en producción.

---

## Próximos pasos recomendados

1. Diseñar tabla/modelo de compliance en backend Story PWA: estado de verificación por partner/firmante.
2. Implementar endpoint Story PWA → Idswyft `POST /api/v2/verify/initialize`.
3. Guardar `verification_id` y estado en Odoo/Story DB.
4. Usar `verification_url` o portal embebido para captura documental.
5. Recibir webhook/callback de Idswyft y actualizar estado de firma en Odoo.

---

## Cómo verificar

```bash
cd /root/Sistema-AI/Vigente/idswyft-spike
docker compose ps
curl -s http://127.0.0.1:18100/health
```

---

## Notas para el receptor

- Ver archivo local `HANDOFF.md` en el spike para detalles completos de endpoints y flujo OTP.
- El developer fue creado con email `storyops+idswyft@storyweproduce.com`.
- El spike comparte volumen de Postgres; revisar backup si se promueve a producción.
