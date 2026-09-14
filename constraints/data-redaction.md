# Redacción de credenciales y datos sensibles

**Estado:** activo  
**Fecha:** 2026-09-13  
**Áreas afectadas:** todos los documentos del workspace, handoffs, decisiones, skills.

---

## Regla

Las credenciales, API keys, tokens, contraseñas, secretos de JWT/encryption y datos personales sensibles nunca se escriben en texto plano en el workspace.

Usar siempre el placeholder:

```
[REDACTED]
```

---

## Forma correcta de documentar

En lugar de:

```
API key: sk-abc123...
```

Escribir:

```
API key: [REDACTED]
Cómo obtenerla: endpoint /api/developer/api-key de Idswyft spike, ver HANDOFF.md.
```

---

## Alcance

- API keys de servicios externos (Odoo, Idswyft, Google, etc.).
- Secrets de `.env` (JWT, DB passwords, encryption keys).
- Tokens de acceso personales.
- Datos biométricos o documentales de verificaciones de identidad.
- Información fiscal o bancaria sensible.

---

## Relaciones

- Relacionado con: `constraints/no-auto-install.md`, decisiones de seguridad.
- Referenciado por: todos los handoffs que contengan credenciales.
