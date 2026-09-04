# einreichung.m-vf.de

Die Einreichungsseite von *Monitor Versorgungsforschung*. Autorinnen und Autoren
stellen hier ihren Beitrag Schritt für Schritt selbst ein, statt sich durch die
WordPress-Oberfläche zu arbeiten.

**Stand: Entwurf.** Die Seite ist noch nicht in Betrieb. Sie speichert nichts auf
einem Server; alle Eingaben bleiben im Browser des Autors (`localStorage`). Der
Knopf am Ende zeigt an, was übergeben *würde*.

## Warum es diese Seite gibt

Das WordPress-Plugin *Medical Monitor* hat ein Einreichungsformular. Es ist
vollständig und kann viel — aber es ist eine Redaktionsoberfläche. Autoren, denen
sie vorgestellt wurde, wollten nicht damit arbeiten: **Wer einmal im Jahr
einreicht, lernt keine Redaktionsoberfläche.**

Diese Seite nimmt den Autor an die Hand. Bei jedem Feld steht, was hineingehört
und wie lang es sein darf. Was fehlt, wird laufend angezeigt, nicht erst beim
Absenden. Am Ende sieht der Autor alles beisammen und gibt es frei — erst dann
geht etwas weg.

## Aufbau

| | |
|---|---|
| `index.html` | die ganze Seite: eine Datei, kein Skript von außen |
| `fonts/` | Lato, wie in den zwölf Knowledge-Hubs |
| `logo/` | Zeichen und MVF-Logo |
| `CNAME` | `einreichung.m-vf.de` |

Keine Abhängigkeiten, kein Bauschritt, kein Generator. Ändern heißt: `index.html`
bearbeiten, committen, pushen.

## Sechs Schritte

1. **Ihr Beitrag** — Rubrik, Vorzeile, Überschrift, Vorspann, Manuskript
2. **Zusammenfassung** — Abstract und Schlagwörter, deutsch und englisch
3. **Abbildungen** — Bilder und Tabellen, jeweils mit Unterschrift
4. **Autoren** — Haupt- und Korrespondenzautor zuerst, dann die Mitautoren
5. **Formales** — Literatur, Zitation, Ausgabe, Lizenz, Interessenkonflikte
6. **Prüfen und freigeben** — Mängelliste, Übersicht, Autorenerklärung

Die Reihenfolge in Schritt 4 trägt eine Information: **Position 1 ist der
Korrespondenzautor.** Ein eigenes Feld dafür gibt es in Medical Monitor bewusst
nicht.

## Was die Seite selbst prüft

- **Längen** — Überschrift 20 bis 100 Zeichen, Vorspann 600 bis 900, Abstracts je
  1.000 bis 1.500. Der Zähler sagt, wie viel noch fehlt, nicht nur wie viel
  dasteht.
- **Schlagwörter** — drei bis sechs je Sprache, mit Komma getrennt.
- **Bildbreite im Browser gemessen**, bevor etwas hochgeht. „300 dpi“ steht in
  einer Bilddatei nur als Notiz und lässt sich ohne Qualitätsgewinn umschreiben;
  prüfbar ist allein die Pixelbreite. Abbildungen brauchen 2.126 px (180 mm bei
  300 dpi), Porträts 354 px (30 mm).
- **Unterschriften** — jede Abbildung und jede Tabelle braucht eine; ein leeres
  Feld bleibt sichtbar markiert.
- **Editorial** steht nicht zur Wahl. Das ist Sache des Herausgebers.
- **Wissenschaft und Wissen gehen ins Peer Review.** Beide Rubriken tragen den
  Hinweis schon in der Auswahlliste, damit die sechs Wochen Vorlauf niemanden
  überraschen.

## Was noch fehlt

**Der Anschluss an WordPress.** Er kann nicht aus dem Browser kommen — das
Anwendungspasswort dürfte dort nicht liegen. Dafür gibt es ein PHP-Skript für den
MVF-Server, gebaut wie `/anmeldung/anmeldung.php`. Es nimmt die Einreichung
entgegen, prüft alles noch einmal (was aus einem Browser kommt, ist eine
Behauptung), lädt die Dateien in die Mediathek und legt den Beitrag als Entwurf
im Typ `abstract` an.

**Die Anmeldung des Autors**, damit ein Zwischenstand auf dem Server liegt und
nicht nur im Browser — und damit ein Autor an einem anderen Gerät weitermachen
kann.

**Zwei Freigaben beim Plugin-Entwickler**, beide je eine Zeile: Der Beitragstyp
`autoren` und die Schlagwortlisten `tag_de`/`tag_en` sind nicht über REST
erreichbar (`show_in_rest` steht nur bei `abstract`). Solange das so ist, landen
Autorenangaben und Schlagwörter lesbar unter „Sonstige Hinweise“ am Beitrag, und
die Redaktion überträgt sie.

## Der Wortlaut der Autorenerklärung

Steht in Schritt 6 und ist **rechtlich bindend, aber noch nicht juristisch
geprüft**. Er muss mit dem übereinstimmen, was das Server-Skript speichert —
sonst bestätigt jemand etwas anderes, als abgelegt wird. Wer ihn ändert, ändert
beide Stellen.

---

*eRelation AG – Content in Health, Bonn · [Impressum](https://www.monitor-versorgungsforschung.de/impressum/)*
