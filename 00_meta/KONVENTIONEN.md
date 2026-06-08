# Konventionen dieser Wissensbasis

> Der lesbare Schema-Vertrag. Hier steht, **welche Ordner es gibt, was wohin
> gehört, wie Dateien heißen und welches Frontmatter Pflicht ist.** Der lokyy-mcp
> erzwingt diese Regeln im Schreibpfad — diese Datei ist die menschenlesbare
> Erklärung dazu (und die Vorlage, wenn ein KI-Agent neue Strukturen anlegt).

## Ordner

| Ordner | Zweck | darf Unterordner |
|---|---|---|
| `RAW/` | Originale, unveränderlich (Single Source of Truth) | ja — z. B. `RAW/transkripte/`, `RAW/sessions/` |
| `RAW/_<name>/` | „Hände weg": durchsucht, aber nie destilliert/geprüft | — |
| `Wiki/` | destillierte, verlinkte Artikel — hier wird gesucht | nein (flach) |
| `Outputs/` | erzeugte Briefings, Reports, Antworten | ja |
| `00_meta/` | Meta: diese Konventionen, später Vorlagen | — |

Pflicht-Dateien: `AGENTS.md`, `CHANGELOG.md`, `RAW/_INGESTED.md` (Register),
`Wiki/INDEX.md`, `Wiki/QUESTIONS.md`.

## Dateinamen

- **RAW-Quellen:** `JJJJ-MM-TT_titel-mit-bindestrichen.md` (Datums-Präfix Pflicht).
- **Wiki-Artikel:** `Slug-Mit-Bindestrichen.md` — der Dateiname **ist** der
  Verweis-Text (`[[Slug-Mit-Bindestrichen]]`), zeichengenau.
- Keine Leer- oder Sonderzeichen, keine Pfadzeichen.

## Frontmatter

**RAW-Quelle** (alle sechs Felder Pflicht, Unbekanntes als `unbekannt`):

```yaml
---
title: <Titel der Quelle>
author: <Urheber oder "unbekannt">
source_url: <Web-Adresse / Publikation oder "unbekannt">
date_added: JJJJ-MM-TT
date_published: JJJJ-MM-TT oder "unbekannt"
type: article | note | video | podcast | book | paper | thread | email | other
---
```

**Wiki-Artikel** (Kopfblock, kein YAML):

```
Status: gesichert | im Aufbau | These
Stand: JJJJ-MM-TT
Quellen: <RAW-Dateiname>, <RAW-Dateiname>   ← Klartext, keine [[Verweise]]
Tags: <wort>, <wort>                          ← optional, einzelne Wörter
```

**Persönliche Notiz** (`RAW/_notizen/`, eigenes leichtes Frontmatter — wird vom
Befehl „neue Notiz" angelegt):

```yaml
---
title: <Titel der Notiz>
date_added: JJJJ-MM-TT
type: note
tags: <wort>, <wort>   ← optional
---
```

Notizen liegen in der „Hände weg"-Zone: durchsuchbar, aber **nie destilliert,
nie geprüft und nicht im Wiki-INDEX**. Sie sind dein persönliches Fach — das
feste Schema oben sorgt dafür, dass sie auffindbar bleiben statt im Wildwuchs zu
verschwinden. Soll eine Notiz fertiges, vernetztes Wissen werden, mach daraus
einen Wiki-Artikel (`artikel_schreiben`).

## Verweise

- `[[Slug]]` gibt es **nur** zwischen Wiki-Artikeln, zeichengenau auf existierende
  Slugs.
- RAW-Quellen werden als **Klartext-Dateiname** zitiert (nie als `[[Verweis]]`) —
  am Datums-Präfix immer erkennbar.

## Reifegrad (Status-Trias)

- **gesichert** — durch mehrere Quellen belegt.
- **im Aufbau** — eine Quelle; wächst noch. (Bei frischen Wissensbasen normal.)
- **These** — eine Vermutung ohne ausreichenden Beleg.
