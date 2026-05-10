<!--
author:    André Dietrich
version:   0.1.0
language:  de
narrator:  Deutsch Male
edit:      true
comment:   Nullius in Verba — Ein 5-Minuten-Lightning-Talk über reaktive OER
           und epistemische Transparenz mit LiaScript.
import:    https://raw.githubusercontent.com/liaTemplates/MicroBit-Simulator/main/README.md
           https://raw.githubusercontent.com/LiaTemplates/Wikimedia/0.0.2/README.md
-->

# Nullius in Verba — Traue nicht dem Autoren

      {{1-2}}
@Wikimedia.embed(https://commons.wikimedia.org/wiki/File:Question_Everything.jpg)

       {{2}}
> ___„Nullius in verba"___ — Nimm niemandes Wort dafür.
>
> -- Royal Society, London, 1660

## Seit der Steinzeit …

    --{{0}}--
Dokumente sind so alt wie die Menschheit. Und sie sehen seit Jahrtausenden gleich aus.

![Die Formel für den Kreisinhalt (A = π · r²) auf sechs historischen Schriftträgern: Stein, Tontafel, Papyrus, Pergament, Papier und PDF — immer dieselbe Formel, immer statisch.](../assets/img/history.jpg)

    --{{1}}--
Gleicher Inhalt. Gleiche Form. Überall. Immer. Du siehst es — aber du kannst es nicht fassen.

      {{1}}
> **Ein Dokument schaut dich an.**
> Du kannst es nicht hinterfragen. Du kannst es nicht verändern.
> Es weiß immer mehr als du.

## Interaktivität

     --{{0}}--
Mithilfe von Computer oder sogar mit "einfachen" Browsern können wir Lernende doch endlich zum echten Verstehen und Experimentieren einladen — oder?

![](https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExMXh0Mmdsc3pobHFscnAxcnE0dHAwMzJsZmZoeDZlODVkdjFlaGdmdSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/DBW3BniaWrFo4/giphy.gif)<!-- style="width: 100%"-->

### Interaktivität == Quiz

    --{{0}}--
Digitale Lehrmaterialien sind oft genau das: statischer Text, PDFs — durch die sich der Lernende quält — und am Ende wartet ein Quiz. Das nennen wir dann interaktiv.

__Für was steht das Kürzel OER?__

- [( )] Online Experience Renderer
- [( )] Openly Editable Repository
- [(X)] Open Educational Resources
- [( )] Optimized E-Reading System

    --{{1}}--
Richtig angeklickt — aber verstanden? Der Inhalt ist gleich, egal ob du die Antwort weißt oder geraten hast. Die Box ist gesetzt. Das Dokument schaut dich an.

      {{1}}
> Lesen. Klicken. Weiter.
> **Checkbox gesetzt. Alles klar?**

### Interaktivität == Code

    --{{0}}--
Das andere Extrem: Notebooks. Code, der wirklich ausgeführt wird. Mächtig — aber Text und Code sind zwei getrennte Welten auf einer Seite.

``` python
from microbit import *
import music

music.play(['f', 'a', 'c', 'e'], wait=False)
display.scroll("Hello LiaScript ...", wait=False)
print("OER is not interactive ... why")
```
@microbit

    --{{1}}--
Du liest — Code unterbricht. Du führst aus — du verlierst den Faden. Text erklärt, Code rechnet. Aber sie sprechen nicht miteinander.

      {{1}}
> **Text ist Text. Code ist Code.**
> Getrennte Welten — auch wenn sie auf derselben Seite stehen.


## Formeln sind stumm

    --{{0}}--
Stell dir vor, du willst verstehen, wie viel CO₂ ein Baum bindet. Hier ist die Antwort — die Formel der Photosynthese:

$$6\, CO_2 + 6\, H_2O \xrightarrow{\text{Licht}} C_6H_{12}O_6 + 6\, O_2$$

    --{{1}}--
Schön. Korrekt. Und völlig stumm. Wie viele Bäume brauche ich, um meine Autofahrten zu kompensieren? Die Formel antwortet nicht. Sie schaut dich an.

      {{1}}
> Statische Dokumente stellen keine Fragen.
> **Sie beantworten auch keine.**

### Bret Victor hatte eine Idee

    --{{0}}--
2013 hat Bret Victor gezeigt, wie Dokumente aussehen könnten — Dokumente, die mitdenken.

!?[Bret Victor — Media for Thinking the Unthinkable](https://www.youtube.com/watch?v=oUaOucZRlmE "Bret Victor — Media for Thinking the Unthinkable (2013)")

    --{{1}}--
In LiaScript ist das Wirklichkeit. Heute. Für alle. Open Source. Und die Präsentation, die ihr gerade seht — das ist selbst ein LiaScript-Dokument.

      {{1}}
> 🔗 [liascript.github.io](https://liascript.github.io)

### 🌳 Wieviel CO₂ binden Bäume?

    --{{0}}--
Schaut her — ein reaktives Dokument. Ändert die Anzahl der Bäume. Alles passt sich an.

Eine Stadt beschließt,
<script input="range" value="10" min="1" max="10000" step="10" output="Bäume">@input</script>
Bäume zu pflanzen, um ihren CO₂-Fußabdruck zu kompensieren. Eine durchschnittliche Autofahrt in Deutschland beträgt ca.
<script input="number" value="400" min="1" max="1000" output="Autofahrt">@input</script> km.
Geht man von einem durchschnittlichen
<script
  input="select"
  output="Autotyp"
  value="SUV (BMW X5)"
  options="EU Neuwagen (2023)|Kompakt-SUV (VW Tiguan)|Mittelklasse-SUV (BMW X3)|SUV (BMW X5)|E-Auto (EU-Strommix)|E-Auto (Ökostrom)"
>"@input"</script>
so beträgt der Verbrauch in etwa
<script output="Verbrauch">
switch ("@input(`Autotyp`)") {
  case "EU Neuwagen (2023)":          118; break
  case "Kompakt-SUV (VW Tiguan)":     160; break
  case "Mittelklasse-SUV (BMW X3)":   185; break
  case "SUV (BMW X5)":         225; break
  case "E-Auto (EU-Strommix)":         70; break
  case "E-Auto (Ökostrom)":             5; break
  default:                            118
}
</script> g/km. __Reicht das — oder ist Bäume pflanzen nur ein grünes Gewissen?__


<script style="display: inline-block; width: 100%">
let trees    = @input(`Bäume`)
let km       = @input(`Autofahrt`)
let g_per_km = @input(`Verbrauch`)  // g CO2/km — kommt vom Select oben

// Wie viel CO2 bindet ein Baum pro Jahr?
// Baumtyp / Kontext	                            CO₂/Jahr
// Junger Baum (1–10 Jahre)	                          1–5 kg
// Durchschnittlicher Laubbaum (mitteleuropäisch)	10–25 kg
// Schnellwüchsiger Baum (Pappel, Eukalyptus)	    20–40 kg
// Oft zitierter "Durchschnitt" in Klimakampagnen	   22 kg (häufig unkritisch übernommen)
// Konservativer wissenschaftlicher Schätzwert	    10–12 kg
let co2_per_tree = 5

let co2_per_trip = km * g_per_km / 1000  // kg CO2 pro Fahrt

let o2_per_tree = Math.round(co2_per_tree * 32 / 44)
let co2_total   = trees * co2_per_tree
let o2_total    = trees * o2_per_tree
let car_trips   = Math.round(co2_total / co2_per_trip)

let option = {
  title: {
    text: trees.toLocaleString('de') + ' Bäume — Wirkung pro Jahr',
    left: 'center'
  },
  tooltip: { trigger: 'axis' },
  grid: { top: 60, left: 90, right: 30, bottom: 50 },
  xAxis: {
    type: 'category',
    data: [
      '🟦 O₂ produziert (kg)',
      '🟩 CO₂ gebunden (kg)',
      '🚗 Fahrten à ' + km.toLocaleString('de') + ' km'
    ]
  },
  yAxis: {
    type: 'value',
    name: 'Menge'
  },
  series: [{
    type: 'bar',
    data: [
      { value: o2_total,  itemStyle: { color: '#5470c6' } },
      { value: co2_total, itemStyle: { color: '#91cc75' } },
      { value: car_trips, itemStyle: { color: '#fac858' } }
    ],
    label: {
      show: true,
      position: 'top',
      formatter: params => params.value.toLocaleString('de')
    }
  }]
}

"HTML: <lia-chart option='" + JSON.stringify(option) + "'></lia-chart>"
</script>

    --{{1}}--
Sieht gut aus, oder? Großartig. Ich habe da ein besonders pessimistisches Beispiel ausgesucht. Aber jetzt: Doppelklick auf das Diagramm und schaut euch den Wert in Zeile 12 an.

