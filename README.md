# Sousveillance-Twitter-Bots

## Was ist ticketfreier ÖPNV und was wollen wir langfristig erreichen?

Infrastruktur für alle
* Komplett Steuer- oder Umlagenfinanziert
* Kosten für die Allgemeinheit sparen:
  * keine Automaten, keine Wartungskosten
  * keine Kontrolleure
  * weniger Verwaltungskosten
  * keine privatisierten Gewinne aus öffentlicher Infrastruktur/natürlichem Monopol
* Weniger komplexes Ticketsystem
  * vor allem für Touristen/Zugezogene gut
  * vor allem, wenn man kein Deutsch spricht
* Weniger Autofahrer
  * wenn die Autofahrer eh mitzahlen, kein Grund mehr Auto zu fahren
  * Gut für die Umwelt
  * weniger Smog, Lärm, Hektik, Verkehrsunfälle
  * weniger Verkehrschaos & Parkplatzsuche
  * Bäume statt Parkplätze
  * weniger Autokult
* Infrastruktur ist besser, je mehr Leute sie nutzen

Demokratische Infrastruktur
* Barrieren für Nutzung sind das eine; Mitbestimmung das andere
* Infrastruktur bestimmt unser aller Leben
* Demokratische Mitbestimmung von Infrastruktur statt privaten Monopolen
* Wird allerdings nicht von Ticketfrei erreicht, sondern ist eher ein Ausblick, siehe Freifunk

## Wie benutzt man Ticketfrei?

Kann ich grade schwarzfahren?
* Auf https://twitter.com/nbg_ticketfrei nachschauen, ob Kontrolleure gesehen wurden
* Mail Notifications - Mailingliste subscriben, und man kriegt immer ne Mail, wenn Kontrolleure gesehen wurden

Wenn man einen Kontrolleur sieht, kann man ihn auf 3 Wegen reporten:
* Eine Mail an nbg_ticketfrei@lists.links-tech.org
* Ein Tweet an @nbg_ticketfrei
* Ein Toot an https://chaos.social/@nbg_ticketfrei

Die Nachricht muss mindestens 1 Wort wie "Konti, Bahn, Bus" etc. enthalten.

Eigentlich ist Ticketfrei einfach nur ein Bot, der retweetet, was man ihm zu fressen gibt.

### Schwachstellen von Ticketfrei

* Funktioniert nur dann wirklich gut, wenn eine kritische Masse mitmacht
  * Aber übt auch bei weniger Leuten schon politischen Druck aus
* Kann natürlich auch missbraucht werden für andere Themen
  * muss man evtl Leute blocken, muss manuell maintained werden
* Falschmeldungen sind unmöglich zu überprüfen
  * richten aber eig auch keinen Schaden an
* Fällt euch noch was ein?

## Wie haben wir Ticketfrei gebaut?

Wie ist Ticketfrei entstanden?

* Wir haben das in Berlin & Hamburg funktionieren sehen und wollten das auch, aber der Code von denen war nicht open source
* Ein Team von 2 Leuten haben sich mal nen Tag hingesetzt, und den Großteil programmiert.
* Später wurde noch etwas verfeinert.
* Der ganze Bot ist auf Github: https://github.com/b3yond/ticketfrei/
  * Dadurch kann der Code nicht nur von jedem genutzt, sondern auch verändert werden.
* Wurde von Laien geschrieben, und hat nicht viel Kenntnisse/Arbeit erfordert - jede*r kann programmieren!
* Und jede*r sollte programmieren - man kann einiges mit Code erreichen.
  * vor allem nicht nur cis-dudes :P

Die Architektur

* 3 python-scripts kümmern sich jeweils darum, auf neue Reports zu hören & sie weiter zu verbreiten:
  * retweetbot.py, retootbot.py, mailbot.py
  * Können jeweils auch einzeln gestartet werden
* ticketfrei.py: Damit kann man alle Bots zusammen ausführen und miteinander reden lassen
* config.toml: Eine zentrale Konfigurationsdatei, um Einstellungen einfach setzen zu können
* trigger.py: Dann gibt es noch eine python-Klasse, die darauf achtet, ob Wörter im Report in der White- oder Blacklist sind:
  * mindestens 1 Wort wie "Konti, Bahn, Bus" muss enthalten sein
  * gewisse antisemitische, sexistische, homophobe Beleidigungen sind geblacklistet
* logger.py: Kümmert sich darum, dass Errors geloggt werden
* sendmail.py: Versendet alle Mails, zB wenn der Bot crasht

Wo wollen wir hin?

* Es soll auch für Leute in anderen Städten einfacher werden, sich Ticketfrei für ihre Stadt zu installieren
* Mit einem Webinterface könnten Leute sich das mit ein paar Knopfdrücken installieren, ohne auf die Kommandozeile zu müssen
  oder einen Server zu brauchen
* Dann können sie sich auf die Promotion-Arbeit konzentrieren, statt aufs technische
* Im Github-Repository gibt es auch Vorlagen für Promotion-Material, das man anpassen kann

## Surveillance vs. Sousveillance

Machen wir da nicht eigentlich Überwachung? Ist das nicht... falsch?

Surveillance / Überwachung
* Kybernetik/Maxwellscher Demon: mit genug Daten ist alles berechenbar?
  * Ob das wirklich funktioniert, spielt keine Rolle
  * These: Um zu beweisen, dass das nicht funktionieren kann, bräuchte man mehr Daten als die Überwacher
* Kybernetik kommt von lat. Kybernetes: Steuermann, Governor. Mit Herrschaft assoziiert
* So viele Daten wie möglich sammeln, um sie verknüpfen zu können
* Geheimhaltung der Daten, um Wissensvorsprung gegenüber anderen Parteien zu haben
* Wird erst gefährlich, wenn die Überwachenden auch Gewalt ausüben können
* Man weiß eigentlich nie, welche Daten andere über einen haben, deswegen schwer sich dagegen zu schützen

Sousveillance / Unterwachung
* Definition Sousveillance:
  * Überwachung von unten nach oben -> Ziel ist mächtiger als man selbst
  * Veröffentlichung der Ergebnisse
* Auch auf Geheimdienste & Polizei hat Beobachtung disziplinierende Wirkung
  * Müssen auf andere Strategien ausweichen, Höhere Kosten
* Geheimhaltung ist immer schwieriger/teurer als Veröffentlichung

Beispiele für Sousveillance
* Whistleblower: Chelsea Manning, Edward Snowden, & WikiLeaks
* (Investigativ-)Journalismus: Was macht denn der Staat eig so?
  * Panama Papers, Paradise Papers
* Bei (Demos etc.) Polizeieinsätze (-gewalt) filmen
  * den größten Zulauf hatte OccupyWallstreet, nachdem Videos von Polizeigewalt auftauchten
  * Das Drama an der Berufsschule war auch deswegen so groß in den Medien, weil die Polizei so eskaliert ist
* Ticketfrei: Wo sind gerade Ticketkontrolleure?

Die Überwachung lässt sich nicht mehr zurückdrehen, und das ist politisch auch nicht gewollt.
Also müssen wir uns wehren, und selbst Gegenüberwachen, um uns vor den Mächtigen zu schützen.
Öffentlichkeit nutzen, statt sich im privaten zu verstecken.

# Vortragsweise

Das ist relativ frontal, und es gibt technische & politische Themen.
Kann für manche schwierig sein, sowas lange zuzuhören.

Gibt aber viel Fragen- & Diskussionspotenzial

Fragen lieber zwischendurch oder am Ende?
* Zwischendurch ist besser für Aufmerksamkeit
* Könnte schwierig sein, fertig zu werden, wenn man zwischendurch Fragen zulässt

Erfahrungswerte?

Um unter Linux die Präsentation zum Laufen zu bringen:

```shell
sudo apt install texmaker texlive-lang-german
texmaker presentation.tex
xdg-open presentation.pdf
```

# Sources

https://pinboard.in/u:jk/t:surveillance/

https://pinboard.in/u:jk/t:tutorial+technology

Michael Seemann (2014): Das Neue Spiel. Strategien für die Welt nach dem digitalen Kontrollverlust, unter http://www.ctrl-verlust.net/buch/
* S. 174+

Ticketfrei Bot:
* How to use: https://github.com/b3yond/ticketfrei/blob/master/guides/use.md
* Promotion Material: https://github.com/b3yond/ticketfrei/tree/master/campaign
