<!--
author:    Jihad Hyadi; Ines Aubel; André Dietrich; Sebastian Zug
version:   0.1.0
language:  de
narrator:  Deutsch Male
edit:      true
comment:   OER-Navigator – Passende Materialien besser finden.
           Hackathon-Pitch beim HackathOERn 2026, Göttingen.
-->

# OER-Navigator – Passende Materialien besser finden

    --{{0}}--
96.000 Ressourcen. Tausende von Lehrenden und Lernenden. Und trotzdem: Der richtige Treffer ist oft Zufall.
Wir fragen uns: Was, wenn die Suche zur Person passt — statt die Person zur Suche?

> **HackathOERn 2026, Göttingen · 13. Mai**
>
> Jihad Hyadi · Ines Aubel · André Dietrich · Sebastian Zug
>
> -- TU Bergakademie Freiberg

## Das Problem

    --{{0}}--
Stell dir vor, du bist Lehramtsstudentin im zweiten Semester. Du weißt, dass es OER gibt.
Du gehst auf OERSI. Du tippst: „Mathe Klasse 5."
Was kommt? Eine Liste. 2.847 Ergebnisse. Sortiert nach — was eigentlich?

      {{1}}
> **Du weißt nicht, wonach du suchst.**
> Du weißt nicht, wie du suchen sollst.
> Du weißt nicht, ob du das Richtige gefunden hast.

    --{{1}}--
Das ist kein Bug. Das ist ein grundlegendes Mismatch-Problem. Auf der einen Seite eine riesige Bandbreite an Ressourcen. Auf der anderen eine riesige Heterogenität von Suchenden — mit völlig unterschiedlichen Intentionen.

      {{2}}
| Wer sucht? | Wonach? | Mit welchem Vorwissen? |
|---|---|---|
| Lernende | orientieren | keins |
| Lehrende | gezielt finden | fachlich |
| Forschende | Materialscouting | methodisch |

    --{{2}}--
Eine Volltextsuche kennt keinen Unterschied. Ein Filterbaum auch nicht. Und ein Graph schon gar nicht.

## Unser Ansatz

    --{{0}}--
Und hier ist unsere These: Die Darstellung muss der Intention folgen — nicht umgekehrt.

      {{1}}
```
Natürlichsprachige Anfrage
         ↓
   Suchsituation klassifizieren
         ↓
   Passende Darstellung auswählen
         ↓  (bei Unklarheit: Rückfrage)
   Ergebnis erleben
```

    --{{1}}--
Bestehende Systeme: eine Darstellung für alle. Graph, Facette oder Volltext — du musst selbst wissen, was du brauchst.
Unser Ansatz: Die Darstellung folgt der Intention. Und wo die Intention unklar ist, wird sie in einem kurzen Dialog geklärt.

      {{2}}
> Das ist der eigentliche didaktische Mehrwert:
> **Nicht nur bessere Ergebnisse — sondern ein sichtbares Suchprofil.**
> Nutzende lernen dabei, was sie eigentlich wollen.

## Die vier Bausteine

    --{{0}}--
Der OER-Navigator besteht aus vier Schichten — jede adressiert einen anderen Teil des Problems.

<div>

### ① Situations-Taxonomie

Entlang der Achsen **Intention × Vorwissen × Rolle** identifizieren wir 5–8 typische Suchsituationen.
Die Taxonomie ist unabhängig vom Prototyp nachnutzbar: als Designprinzip für Portale und Repositorien.

### ② LLM-Klassifikator

Ein Prompt-Engineering-Ansatz mit Few-Shot-Beispielen aus einem Eval-Korpus.
Ordnet eine natürlichsprachige Anfrage einer Situation zu — und extrahiert Parameter wie Thema, Niveau und Format.

### ③ Dialogischer Rückfragemodus

Bei Unsicherheit stellt das System **eine gezielte Rückfrage pro unklarer Achse**.
Ergebnis: ein sichtbares Suchprofil, das Nutzende ihre eigene Intention erfahren lässt.

### ④ Visualisierungs-Katalog + Zuordnungsmatrix

Kuratierte Sammlung von Zugangsformen — Themenlandkarte, Lernpfad-DAG, facettierte Suche, Recommender, Zeitstrahl …
Mit begründeter Zuordnung: **welche Darstellung für welche Situation — und warum nicht die andere.**

</div>

    --{{1}}--
Der konzeptionelle Höhepunkt ist ein Plenums-Matrix-Workshop: alle mappen gemeinsam Situationen mal Darstellungen — und begründen, warum nicht die andere.

      {{1}}
> 🔑 Kernfrage des Workshops:
>
> Welche Darstellung passt zu welcher Situation —
> **und warum schadet eine andere dort aktiv?**

## Unsere Ziele nach 3 Tagen

    --{{0}}--
Drei Tage. Vier Schichten. Was wollen wir am Ende vorweisen?

      {{1}}
- 📄 **Situations-Taxonomie** — publizierbar, im Plenum "peer-reviewt", direkt nachnutzbar
- 🗂️ **Visualisierungs-Katalog mit Begründungsmatrix** — Situation → Darstellung, unabhängig vom Code
- 🖥️ **Lauffähiger Prototyp** — Eingabe → Klassifikation → passende Darstellung
- 💬 **Galerie von Rückfrage-Vorlagen** — wiederverwendbares Scaffolding-Muster

    --{{1}}--
Datenbasis: OERSI — 96.000 Ressourcen, offene Elasticsearch-API, AMB-Metadaten.
Der Prototyp soll ab Tag 1 gegen reale Inhalte laufen — kein synthetisches Mini-Korpus.

      {{2}}
> **Fallback bei Zeitdruck:**
>
> Statt der vollen Matrix — 2 Situationen × 2 Darstellungen als vollständig demonstrierbares Szenario.

    --{{2}}--
Die nachhaltigsten Artefakte sind übrigens nicht der Code — sondern die Taxonomie und die Zuordnungsmatrix.
Die funktionieren ohne Server, ohne API, ohne Prompt. Die sind einfach wahr.

## Mach mit

    --{{0}}--
Der OER-Navigator ist ein Anfang — kein Produkt. Und Anfänge brauchen Menschen, die weitermachen.

      {{1}}
<div>

### Wo wir Hilfe brauchen

- 🔬 **Validierung der Taxonomie** — Passt sie für andere Fächerkulturen? Andere Repositorien?
- 🎨 **UX-Perspektive** — Wie erlebt man das Suchprofil? Was ist zu viel Rückfrage?
- 🔗 **Integration** — Welche Repositorien sind offen für sowas? Wo gibt es Schnittstellen?
- 💡 **Weitere Situationen** — Was haben wir vergessen?

</div>

    --{{1}}--
Alles wird auf GitHub landen. Die Taxonomie, die Matrix, der Prototyp. Alles offen. Alles nachnutzbar.

      {{2}}
> 🔗 **github.com/[repo]** ← kommt noch
>
> Fragen? Ideen? Kritik? Jetzt — oder in den nächsten drei Tagen.

    --{{2}}--
Danke. Und jetzt: Wer hat eine Suchanfrage, die wir unbedingt in unser Eval-Korpus aufnehmen sollten?
