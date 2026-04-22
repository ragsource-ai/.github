# RAGSource

**RAGSource** ist eine Open-Source-Engine für Agentic RAG mit strukturierten Wissensquellen — entwickelt für den Einsatz in Verwaltung, Kommunen und Organisationen mit komplexen Regelwerken.

[![License: MIT](https://img.shields.io/badge/server-MIT-green.svg)](https://github.com/ragsource-ai/ragsource-server/blob/main/LICENSE)
[![License: CC BY 4.0](https://img.shields.io/badge/content-CC%20BY%204.0-lightgrey.svg)](https://github.com/ragsource-ai/ragsource-content/blob/main/LICENSE)
[![Rechtstexte](https://img.shields.io/badge/Rechtstexte-621%2B-blue.svg)](https://github.com/ragsource-ai/ragsource-content)

---

## Was ist RAGSource?

LLMs halluzinieren, wenn sie aus dem Gedächtnis arbeiten. RAGSource löst das für strukturierte Wissensdomänen: Gesetze, Satzungen, interne Richtlinien, Verträge, Akten.

Das System nutzt **hierarchisches Retrieval**: Der KI-Assistent navigiert selbständig von einer Quellenübersicht (Catalog) über das Inhaltsverzeichnis (TOC) zu den exakten Paragraphen — und zitiert immer aus dem Originalwortlaut.

```
LLM → RAGSource_catalog → RAGSource_toc → RAGSource_get (§-granular)
```

**Normenhierarchie ist eingebaut:** EU → Bund → Land → Kreis → Verband → Gemeinde. Bei Konflikten zwischen Quellen benennt der Assistent die höherrangige Norm.

---

## Repositories

| Repository | Beschreibung |
|-----------|-------------|
| [ragsource-server](https://github.com/ragsource-ai/ragsource-server) | MCP-Server (Cloudflare Workers + D1) — der Kern des Systems |
| [ragsource-content](https://github.com/ragsource-ai/ragsource-content) | 621+ öffentliche Rechtstexte als strukturiertes Markdown |

---

## Live-Deployments

| Anwendung | URL | Beschreibung |
|-----------|-----|-------------|
| **amtsschimmel.ai** | [mcp.amtsschimmel.ai/mcp](https://mcp.amtsschimmel.ai/mcp) | Kommunales Verwaltungsrecht Deutschland |
| **brandmeister.ai** | [mcp.brandmeister.ai/mcp](https://mcp.brandmeister.ai/mcp) | Feuerwehr- und Gefahrstoffrecht |
| **paragrafenreiter.ai** | [mcp.paragrafenreiter.ai/mcp](https://mcp.paragrafenreiter.ai/mcp) | Alle Quellen, kein Tenancy-Filter |

---

## Anwendungsfälle

- **Kommunalverwaltungen** — Satzungen, Gemeindeordnung, Kreisrecht, Bundesrecht
- **Feuerwehr & Gefahrenabwehr** — FwDV, Brandschutzrecht, Gefahrstoffdaten (14.936 Stoffe)
- **Öffentliche Einrichtungen** — Tarifrecht (TVöD, TV-L, AVR), Dienstanweisungen
- **Compliance-Assistenten** — Normenhierarchie-bewusstes Retrieval für rechtssichere Antworten

---

## Architektur

Der **Server** läuft als Cloudflare Worker und stellt Rechtstexte per MCP bereit. Das **Content-Repo** enthält die Quellen als Markdown mit YAML-Frontmatter — CI/CD baut die Datenbank automatisch neu. Neue Inhalte sind innerhalb von **2 Minuten** live.

---

## Loslegen

```bash
git clone https://github.com/ragsource-ai/ragsource-server
cd ragsource-server && npm install && npm run dev
```

MCP-URL in Claude.ai, Claude Desktop oder Langdock eintragen — fertig.

---

## Lizenz

MIT (Code) · CC-BY 4.0 (Inhalte) · [Powered by RAGSource](https://github.com/ragsource-ai)
