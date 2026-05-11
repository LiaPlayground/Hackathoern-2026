# OER-Navigator — Konzeptnotizen (Stand: 11. Mai 2026)

> Ergebnis der Hackathon-Arbeitssitzung. Ergänzt den bisherigen Pitch-Scope um die NOSTR-Dimension.

---

## 1. Kernidee (neu: Scope-Erweiterung heute)

Der OER-Navigator kombiniert ab sofort **zwei Quellen**:

| Quelle | Was kommt? | Warum? |
|---|---|---|
| **OERSI** (bestehend) | Materialien, Metadaten (AMB), Volltextsuche | 96.000 Ressourcen, offene API |
| **NOSTR** (neu) | Events, Gruppen, Personen/Autoren, Communities | Kontextinformationen zur Community |

**Grundprinzip:** Wer nach OER sucht, sucht nicht nur Material — er sucht auch nach Kontext: Wer arbeitet zu diesem Thema? Gibt es ein Event dazu? Welche Community ist aktiv?

---

## 2. Was die NOSTR-Erweiterung konkret liefert

Zu einer Suchanfrage werden **parallel** angezeigt:

- **Materialien** (OERSI-Ergebnisse, klassifiziert und dargestellt nach Suchsituation)
- **Events** — z.B. Workshops, Tagungen, Kurse zum Thema (aus NOSTR)
- **Gruppen / Communities** — wer ist zu diesem Thema aktiv?
- **Personen / Autoren** — Abonnement-Möglichkeit von Inhalten bestimmter Produzenten
- **Empfehlungen** — community-basiert: Likes, Reposts, kuratierte Sammlungen

**Plattform-Referenz:** [edufeed.org](https://edufeed.org/) / [dev.edufeed.org](https://dev.edufeed.org/)  
**Graph-Explorer (Referenz):** [edufeed-org.github.io/nostr-graph-explorer](https://edufeed-org.github.io/nostr-graph-explorer/)

---

## 3. Personas für den Demonstrator

### Persona A — Lehrerin für Demokratiebildung

**Arbeitstitel:** Anna Berger  
**Quelle:** [Persona-Pad](https://pad.gwdg.de/JnlpSM6vQvapj1oGAfAF4A)

- Lehrt Demokratiebildung als Querschnittskompetenz
- Sucht Materialien für konkrete Unterrichtssituationen (nicht thematisch abstrakt)
- **Typische Suchanfragen:**
  - „Pilgern Grundschule Ostern"
  - „Demokratie Abstimmung Klasse 6 partizipativ"
- **Was sie braucht (zusätzlich zu Material):**
  - Events: Wann gibt es Fortbildungen / Fachtagungen zum Thema?
  - Communities: Wer macht ähnliches? Gibt es Netzwerke?
  - Aktualität: Wie aktuell sind die Materialien?
- **Suchsituation:** Problemorientiert + inspirationsgetrieben
- **Visualisierung:** Cards mit Snippets + Community-Sidebar (Events, Gruppen)

---

### Persona B — Studienanfänger (Mathevorkurs)

- Erstes Semester, kaum Vorwissen über OER und Suche
- Sucht orientierend, nicht zielgerichtet
- **Typische Suchanfragen:**
  - „Grundstudium Mathematik Vorkurs Beweise"
  - „Mathe Anfänger Übungen Analysis"
- **Was er braucht (zusätzlich zu Material):**
  - Studiengruppen zu seinem Thema (NOSTR communities)
  - Events: Gibt es Tutorien, Online-Kurse, Lerngruppen?
  - Einstiegspunkte: Kuratierte Sammlungen statt rohe Trefferlisten
- **Suchsituation:** Orientierend, geringes Vorwissen
- **Visualisierung:** Themenlandkarte / Lernpfad + Gruppenempfehlungen

---

## 4. Klassifikations-Achsen (aktualisiert)

Die drei Achsen aus dem bisherigen Pitch bleiben — aber NOSTR-Ergebnisse werden als **vierte Schicht** ergänzt:

```
Suchanfrage (natürlichsprachig)
     ↓
LLM-Klassifikator → Situation (Intention × Vorwissen × Rolle)
     ↓
Darstellung (OERSI-Ergebnisse) + Community-Layer (NOSTR-Ergebnisse)
     ↓              ↓
Materialien    Events / Gruppen / Personen
```

---

## 5. Intentionen (erweitert um Community-Dimension)

| Intention | Beispielanfrage | OER-Ergebnis | NOSTR-Ergänzung |
|---|---|---|---|
| Inspiration | „Statistik für Einsteiger" | Materialsammlung, Themenlandkarte | Communities, Autoren |
| Problemorientiert | „Studierende sollen aktiv mit Daten arbeiten" | Aktivierungsformate, Aufgaben | Events, Fortbildungen |
| Eigenschaftssuche | „CC-BY Videos Machine Learning Deutsch" | gefilterte Trefferliste | Kanäle, Serien |
| Recherche | „Alles zu KI inkl. AI, maschinelles Lernen" | Synonyme-Suche via DNB-Schlagworte | Fach-Communities |
| Orientierung | „Mathevorkurs Beweise" | Lernpfad / kuratierte Sammlung | Studiengruppen, Tutorien |

---

## 6. Offene Fragen / nächste Schritte

- [ ] Persona A (Anna Berger) ausführlicher ausarbeiten — Pad-Dokument auswerten
- [ ] NOSTR-Datenmodell klären: Welche Event-Typen sind relevant? (Kalender-Events, Gruppen, Reposts?)
- [ ] Demonstrator-Scope: 2 Personas × 2 Situationen als Mindest-Demo
- [ ] OERSI + NOSTR: Wie werden Ergebnisse kombiniert dargestellt? (Tabs? Sidebar? Karten-Mix?)
- [ ] OERSI-API-Zugang bestätigen (Elasticsearch, AMB-Metadaten)
- [ ] edufeed.org API / NOSTR-Relay-Zugang klären

---

## 7. Relevante Links

| Ressource | URL |
|---|---|
| Hackathon Konzept (PDF, S.2-3) | https://github.com/LiaPlayground/Hackathoern-2026/blob/main/assets/pdf/Hackathon_Concept.pdf |
| edufeed.org | https://edufeed.org/ |
| edufeed Kalender | https://dev.edufeed.org/calendar |
| edufeed Community "Hackathoern 2026" | https://dev.edufeed.org/c/npub1lcvcmzvw452sd4jen7r3j0za60pzawach6nyyws0094ltz2ezr5qae6xhj |
| NOSTR Graph Explorer | https://edufeed-org.github.io/nostr-graph-explorer/ |
| OERSI | https://oersi.org |
| TUBAF Connected Lecturer Data | https://tubaf-ifi-connectedlecturer.github.io/Data/ |
| Persona Anna Berger (Pad) | https://pad.gwdg.de/JnlpSM6vQvapj1oGAfAF4A |
| LiaScript | https://liascript.github.io/ |
| Hackathon Repo | https://github.com/LiaPlayground/Hackathoern-2026/tree/main |
