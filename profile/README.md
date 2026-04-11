# RAGSource

**RAGSource** ist eine Open-Source-Engine für Agentic RAG mit strukturierten Wissensquellen — entwickelt für den Einsatz in Verwaltung, Kommunen und Organisationen mit komplexen Regelwerken.

---

## Was ist RAGSource?

LLMs halluzinieren, wenn sie aus dem Gedächtnis arbeiten. RAGSource löst das für strukturierte Wissensdomänen: Gesetze, Satzungen, interne Richtlinien, Verträge, Akten.

Das System nutzt **hierarchisches Retrieval**: Der KI-Assistent navigiert selbständig von einer Quellenübersicht (Catalog) über das Inhaltsverzeichnis (TOC) zu den exakten Paragraphen — und zitiert immer aus dem Originalwortlaut.

```
LLM → RAGSource_catalog → RAGSource_toc → RAGSource_get (§-granular)
```

**Normenhierarchie ist eingebaut:** EU → Bund → Land → Kreis → Verband → Gemeinde → Intern. Bei Konflikten zwischen Quellen benennt der Assistent die höherrangige Norm.

---

## Repositories

| Repository | Beschreibung |
|-----------|-------------|
| [ragsource-server](https://github.com/ragsource-ai/ragsource-server) | MCP-Server (Cloudflare Workers + D1) — der Kern des Systems |
| [ragsource-content](https://github.com/ragsource-ai/ragsource-content) | Öffentliche Rechtstexte als strukturiertes Markdown (378+ Quellen) |

---

## Anwendungsfälle

RAGSource ist eine generische Engine. Typische Einsatzszenarien:

- **Kommunalverwaltungen** — Satzungen, Gemeindeordnung, Kreisrecht, Bundesrecht
- **Öffentliche Einrichtungen** — Tarifrecht (TVöD, TV-L), Dienstanweisungen
- **Organisationen mit Regelwerken** — Interne Richtlinien kombiniert mit externem Recht
- **Compliance-Assistenten** — Normenhierarchie-bewusstes Retrieval für rechtssichere Antworten

> **amtsschimmel.ai** ist eine Anwendung, die auf RAGSource aufbaut — spezialisiert auf kommunales Verwaltungsrecht in Deutschland.

---

## Architektur in 3 Sätzen

Der **Server** läuft als Cloudflare Worker und stellt öffentliche Rechtstexte per MCP bereit. Das **Content-Repo** enthält die Quellen als Markdown mit YAML-Frontmatter — CI/CD baut die Datenbank automatisch neu.

---

## Loslegen

```bash
# Server lokal starten (Cloudflare Workers)
git clone https://github.com/ragsource-ai/ragsource-server
cd ragsource-server && npm install && npm run dev
```

MCP-URL in Claude.ai / Claude Desktop / Langdock eintragen — fertig.

---

## Lizenz

MIT (Code) · CC-BY 4.0 (Inhalte/Prompts) · [Powered by RAGSource](https://github.com/ragsource-ai)
