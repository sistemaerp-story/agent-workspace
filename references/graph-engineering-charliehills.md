# Referencia — Graph Engineering para Claude Code

- **Fuente:** Charlie Hills, *Graph engineering (for normal people)*
- **URL:** https://charliehills.substack.com/p/graph-engineering-claude-code
- **Fecha de captura:** 2026-09-13
- **Propósito para StoryWeProduce:** metodología para mapear carpetas de trabajo, detectar archivos huérfanos y anclar contexto antes de cada job de agente.

---

## Problema

El autor descubrió que el 78% de sus documentos no eran referenciados por ningún otro archivo. Para la IA, un archivo no referenciado es prácticamente invisible: igual que si no existiera.

---

## Solución: 4 prompts

### Prompt 1 — Mapear la carpeta

> Read every single file in [THIS FOLDER] and build me a map of it.
> For each one, work out what it is about and which other files cover the same ground.
>
> PART ONE: every topic you found, and the files covering it, ranked by how many other files point at it.
> PART TWO: how many files nothing points at, as a number and as a percentage of the folder.
> PART THREE: the connections I would not have spotted myself, naming which two files each one joins and why you joined them.
> PART FOUR: a header saying how many files you read, and today's date.
>
> Mark every connection FOUND, meaning both files state it, or GUESSED, meaning you inferred it.

### Prompt 2 — Verificar conexiones

> Go through the map and check whether each connection is actually stated by both files or only inferred.
> Update the map so every connection is labeled FOUND or GUESSED.

### Prompt 3 — Proponer fixes

> Look at the orphan files and conflicting connections.
> Propose specific fixes: move files, merge duplicates, add links, delete outdated content.
> Estimate effort and impact for each fix.

### Prompt 4 — Anclar el mapa

> Add this line to the top of the CLAUDE.md in this folder:
> "READ [map-filename].md BEFORE ANY JOB IN THIS FOLDER, AND APPEND WHAT YOU LEARNED WHEN YOU FINISH."

---

## Aplicación al agent-workspace

- Revisar periódicamente `handoffs/`, `decisions/`, `references/` y `skills/` para detectar contenido huérfano.
- Crear mapas locales por proyecto en `projects/`.
- Considerar un `CLAUDE.md` o `AGENTS.md` por carpeta para cargar contexto antes de trabajar.
- Usar FOUND/GUESSED como etiqueta de confianza de las conexiones entre documentos.

---

## Notas

- Método manual orientado a Claude Code; adaptable a Hermes y al ecosistema Story.
- Complementa graphify (knowledge graph automático del repo) con una técnica de limpieza de documentos.
