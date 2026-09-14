# Referencia — Build a company brain (Charlie Hills)

- **Fuente:** Charlie Hills, *Build a company brain in four files*
- **URL:** https://charliehills.substack.com/p/graph-engineering-claude-code (imagen adjunta en comentario de issue #1)
- **Fecha de captura:** 2026-09-14
- **Propósito para StoryWeProduce:** definir los 4 archivos base del conocimiento del negocio que todos los agentes deben leer antes de trabajar.

---

## Metodología

Construir un "cerebro de empresa" en 4 archivos Markdown, cada uno generado con un prompt específico. Los agentes leen estos archivos antes de cualquier tarea de marketing, ventas, producto o comunicación.

---

## Los 4 archivos

| Archivo | Propósito | Contenido |
|---|---|---|
| **company.md** | THE BUSINESS | Quién es la empresa, qué hace, para quién, cómo se expresa, qué rechaza. |
| **customer.md** | THE BUYER | Cliente ideal, mensajes reales, palabras que usa, objeciones, qué se ha entendido mal. |
| **offer.md** | THE DEAL | Qué se vende, precios, qué incluye y qué no, cómo empieza un cliente, citas exactas. |
| **voice.md** | THE VOICE | Patrones de escritura medidos en números: aside brackets, párrafos que inician con and/but/so, contracciones, ratio de "I am against you", frases típicas verbatim. |

---

## Proceso de construcción

Para cada archivo:

1. **Gather the evidence** — reunir páginas, posts, mensajes, propuestas, precios.
2. **Paste it in, named** — pegar la evidencia en el chat con nombre/etiqueta.
3. **Paste prompt** — ejecutar el prompt específico del archivo.
4. **Check the brackets/table** — verificar citas y mediciones.
5. **Save it as `.md`** — guardar en la carpeta del workspace.

---

## Prompts originales

### company.md

> Read the about page and posts I have pasted. Write company.md in my words:
> 1. WHAT WE DO. Quote me, do not summarise me.
> 2. WHO IT IS FOR. The people my posts speak to.
> 3. WHAT WE REFUSE. Only if I said it somewhere.
> 4. HOW WE SAY IT. Three lines I actually wrote.
> 5. CITE EVERY LINE. [post 14], [about page].

### customer.md

> Here is my ideal customer, then real messages. Write customer.md:
> 1. WHO THEY ARE. Job title and company size.
> 2. WHAT THEY WANT. In their words.
> 3. WHAT THEY ARE STUCK ON. Most common first.
> 4. THE WORDS THEY USE. Word for word.
> 5. WHAT I GOT WRONG. Where the messages disagree.

### offer.md

> Read the offer page, price list and proposals I have pasted. Write offer.md:
> 1. WHAT I SELL. One line each.
> 2. THE PRICE. Word for word from the document.
> 3. WHAT IS INCLUDED. And what is not.
> 4. WHAT HAPPENS NEXT. How a client starts.
> 5. CITE EVERY LINE. Conflicts listed, never pick one.

### voice.md

> Read everything I have pasted. Measure how I write, in numbers, into voice.md:
> 1. BRACKETED ASIDES. Per 1,000 words.
> 2. PARAGRAPHS OPENING AND, BUT, SO.
> 3. CONTRACTIONS. Per 1,000 words.
> 4. I AM AGAINST YOU. Per 1,000 words, as a ratio.
> 5. FIVE TYPICAL SENTENCES. Verbatim, numbered.

---

## Adaptación para StoryWeProduce

| Archivo | Aplicación a Story |
|---|---|
| `company.md` | StoryWeProduce: qué hace (producción audiovisual + ERP/PWA), para quién, qué rechaza, voz de Jorge. |
| `customer.md` | Clientes de producción: directores de marca, agencias, productoras, anunciantes; sus mensajes y objeciones. |
| `offer.md` | Servicios de producción, propuestas, flujos de contratación, alcances, precios. |
| `voice.md` | Tono de comunicación de Story: directo, sin relleno, técnico pero explicable, español de negocios México. |
| `user.md` | Perfil de Jorge Medina: preferencias, estilo de trabajo, decisiones frecuentes, qué valora, qué rechaza. |

---

## Ubicación propuesta en el workspace

```
business/
├── company.md
├── customer.md
├── offer.md
├── voice.md
└── user.md   # perfil de Jorge / operador principal
```

---

## Notas

- Los prompts priorizan **citas verbatim** y **evidencia real**, no resúmenes genéricos.
- `voice.md` es cuantitativo: mide patrones de escritura, no impresiones subjetivas.
- `user.md` fue añadido por Jorge para capturar preferencias y contexto del operador humano principal.
- Esta referencia debe usarse para crear la carpeta `business/` en EPIC-1.
