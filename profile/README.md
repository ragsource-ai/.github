# RAGSource

**RAGSource** ist ein Open-Source-Framework für Agentic RAG mit strukturierten Wissensquellen — entwickelt für den Einsatz in Verwaltung, Kommunen und Organisationen mit komplexen Regelwerken.

[![License: AGPL v3](https://img.shields.io/badge/server-AGPL%20v3-blue.svg)](https://github.com/ragsource-ai/ragsource-server/blob/main/LICENSE)
[![License: ODbL](https://img.shields.io/badge/Rechtstexte-ODbL-brightgreen.svg)](https://github.com/ragsource-ai/ragsource-content/blob/main/LICENSE)
[![License: CC BY-SA 4.0](https://img.shields.io/badge/Skills-CC%20BY--SA%204.0-lightgrey.svg)](https://github.com/ragsource-ai/ragsource-content/blob/main/LICENSE)

---

## Was ist RAGSource?

LLMs halluzinieren, wenn sie aus dem Gedächtnis arbeiten. RAGSource löst das für strukturierte Wissensdomänen: Gesetze, Satzungen, interne Richtlinien, Verträge, Akten.

Das System nutzt **hierarchisches Retrieval**: Der KI-Assistent navigiert selbständig von einer Quellenübersicht über das Inhaltsverzeichnis zu den exakten Paragraphen — und zitiert immer aus dem Originalwortlaut.

```
LLM → rag_legal → rag_contents → rag_read (§-granular)
                               → rag_db_query (strukturierte Daten)
```

**Normenhierarchie ist eingebaut:** EU → Bund → Land → Kreis → Verband → Gemeinde. Bei Konflikten zwischen Quellen benennt der Assistent die höherrangige Norm.

Neben Rechtstexten enthält das System **Skills** — domänenspezifische LLM-Handlungsanleitungen für Einsatztaktik, Gefahrstoffabfragen, Rechtsfragen u.v.m.

---

## Repositories

| Repository | Beschreibung |
|-----------|-------------|
| ragsource-server | MCP-Server (Cloudflare Workers + D1) — der Kern des Systems |
| ragsource-content | Öffentliche Rechtstexte + Skills als strukturiertes Markdown |

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
- **Feuerwehr & Gefahrenabwehr** — FwDV, Brandschutzrecht, Gefahrstoffdaten
- **Öffentliche Einrichtungen** — Tarifrecht (TVöD, TV-L, AVR), Dienstanweisungen
- **Compliance-Assistenten** — Normenhierarchie-bewusstes Retrieval für rechtssichere Antworten

---

## Architektur

Der **Server** läuft als Cloudflare Worker und stellt Rechtstexte per MCP bereit. Das **Content-Repo** enthält die Quellen als Markdown mit YAML-Frontmatter — CI/CD baut die Datenbank automatisch neu. Neue Inhalte sind innerhalb von **2 Minuten** live.

---

## Interesse?

Anfragen zu Pilotprojekten, Lizenzen oder technischer Integration: [christian@ragsource.ai](mailto:christian@ragsource.ai)

---

## Lizenz

AGPL v3 (Code) · ODbL v1.0 (Rechtstexte) · CC-BY-SA 4.0 (Skills/Prompts) · [Powered by RAGSource](https://github.com/ragsource-ai) · [Impressum](https://github.com/ragsource-ai/.github/blob/main/profile/LEGAL.md)

---

<p align="center">
  <br>
  Made with ❤️ for Open Source AI
  <br><br>
  This project started from a personal need: reliable, citable knowledge<br>
  for firefighters, public servants, and everyone who needs to get things right.<br>
  <br>
  <strong>It belongs to everybody.</strong>
</p>
