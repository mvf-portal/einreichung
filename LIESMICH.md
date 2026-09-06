# einreichung.m-vf.de

**Dieses Repo ist seit dem 06.09.2026 nur noch eine Weiterleitung.**

Die Einreichungsseite selbst liegt auf dem MVF-Server:

| | |
|---|---|
| Autorenseite | <https://www.monitor-versorgungsforschung.de/einreichung/> |
| Redaktionsansicht | <https://www.monitor-versorgungsforschung.de/einreichung/intern/> |
| Endpunkt | `/einreichung/einreichung.php` |

## Warum sie dort liegen muss

Der Endpunkt lädt WordPress über `wp-load.php` **direkt**. Das war der Umbau,
der die Sache überhaupt zum Laufen gebracht hat: Der vorherige Weg über die
REST-Schnittstelle rief die eigene öffentliche Adresse auf, lief damit über
Cloudflare und bekam dessen Bot-Prüfung als Antwort — HTML statt JSON, gelesen
als 403.

Direkt laden geht nur aus demselben Verzeichnisbaum heraus. Eine Subdomain auf
einen eigenen Server zu legen hätte genau diesen Zugriff gekostet; die
Alternative wäre ein Proxy gewesen. Deshalb: eine Adresse, ein Ordner.

## Warum diese Weiterleitung trotzdem bleibt

Die kurze Adresse steht in gedruckten Heften und in Mails. Sie einfach sterben
zu lassen hieße, dass jemand mit einem Heft in der Hand vor einer
Fehlermeldung steht.

## Wo die Quelle liegt — und warum unter `_quelle/`

Die eigentliche Seite steht in `_quelle/index.html`. Der Unterstrich ist kein
Geschmack: GitHub Pages läuft hier mit Jekyll, und Jekyll veröffentlicht
Verzeichnisse mit führendem Unterstrich nicht. Damit ist ausgeschlossen, dass
hier je eine zweite, veraltete Fassung der Seite erreichbar ist.

Genau das war nämlich passiert. Am 06.09.2026 stand unter dieser Adresse
stundenlang ein Formular ohne die Rubriken *Kongressnachbericht* und
*Sonderdruck*, während der Server sie schon kannte — ein Autor hätte etwas
einreichen können, das der Endpunkt gar nicht mehr annimmt.

## Ändern und ausliefern

1. `_quelle/index.html` bearbeiten, committen, pushen.
2. Die Datei als `index.html` nach `/einreichung/` auf den MVF-Server legen,
   zusammen mit `fonts/` und `logo/`, falls die sich geändert haben.

Es gibt keinen Bauschritt und keine Abhängigkeit von außen — eine Datei, die
Schrift daneben.

Die Redaktionsansicht hat ein eigenes Repo (`einreichung-intern`); dort
erzeugt ein Skript aus der `index.html` die `index.php` mit Anmeldung.

---

*eRelation AG – Content in Health, Bonn*
