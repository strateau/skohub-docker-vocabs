# Publikation eines kontrollierten Vokabulars mit SkoHub Vocabs

MALIS 23.2 IT 2

Prüfer: Adrian Pohl

Gruppe:
Carlos Berbil Ceballos, Marcus Peter, Ruben Treiber


## **1. Beschreibung des gewählten Vokabulars**

Für die Bearbeitung des kleinen Projekts entschieden wir uns für ein Vokabular, das in der USB Köln zur Klassifikation des Bestandes im Lesesaal verwendet wird.

Da die USB Köln ihre thematisch-hierarchische Aufstellungssystematik ihres Lesesaals im Rahmen des Projekts OpenBib (https://www.openbib.org/) veröffentlicht hat, liegt es bereits als yaml veröffentlicht vor (https://github.com/oflimm/openbib/blob/master/portal/perl/conf/usbls.yml).
Dieses yaml gibt die basale Informationen die Signatur und deren Bezeichnung wieder (z.B. K1-, Archäologie und Antike Kunst).
Im Gegensatz zur Homepage der USB Köln liegt die Systematik jedoch beispielsweise nicht englischsprachig vor (vgl.https://katalog.ub.uni-koeln.de/portal/browse/ls/id/K.html?l=en).
Ein möglicher erster Nutzen einer Publikation und Rückübertragung des Vokabulars mit SkoHub Vocabs könnte die deutsch-englische Zweisprachigkeit der Signaturbereiche sein. 

Wie der Autor der Aufstellungssystematik Oliver Flimm uns mitteilte, sind die Signaturbereiche des Lesesaals nicht abgeschlossen. Es können Medien hinzukommen oder aussortiert werden. Außerdem können zusätzliche Bereiche hinzukommen. Da die Bereiche jeweils numerisch mit Start- und Endnummern eingegrenzt wurden, definiert die Notation die Maximalanzahl an möglichen Titeln. Eine Folge daraus ist, dass das Problem derzeit mit inkonsistenten Notationen umgangen wird. 

Das Vokabular des Lesesaals besteht aus etwa 800 Deskriptoren, befindet sich in zwei Hierachiestufen und liegt wie erwähnt auf deutsch vor. Die höchste Hierarchiestufe betitelt die USB Köln mit "Fachgebiete", die darunterliegende Ebene mit "Grundsignaturen und Untergebiete".

<span style="color:red">Die Bearbeitung der Aufgabe erfolgte händisch, da uns die Auseinandersetzung mit SkoHub Vocabs so direkter und einprägsamer erschien.</span> Insgesamt wurden 46 Deskriptoren übertragen und um englische Übersetzungen ergänzt.


## **2. Zusammenarbeit mit GitHub**

Zur Zusammenarbeit im Projekt nutzten wir ein Kanban Board auf Github. Dabei arbeiteten wir nicht mit Fristen, sondern mit Zuständigkeiten unter der Maßgabe des "alsbald/demnächst zu erledigen". Das detaillierte Besprechen der Augaben erfolgte dagegen über Zoom.

Da keine Erfahrungen in der Zusammenarbeit mittels Kanban auf Github vorhanden waren, gab es schon beim Einrichten grundlegende Lerneffekte. Die Bedienung erwies sich als einfach. Weitergehende Funktionen blieben allerdings vermutlich ungenutzt. 
Eine spezifischere Form des Projektmanagements ("agil" etc.) wurde ausdrücklich nicht verfolgt. Die Festlegung abgegrenzter Aufgaben gestaltete sich einfach, die überliegende Hierarchieebene und die beiden unterliegenden Ebenen wurden jeweils von einer Person bearbeitet.

Die Arbeiten in Github selbst - das Forken von Repos etc. - liefen als nicht definierte Aufgaben im Hintergrund und wurden im Laufe des Projekts von allen Gruppenmitgliedern wahrgenommen. Gangbarer Weg war schließlich, die Gruppenmitglieder in das Projekt einzuladen, um Änderungen direkt vornehmen zu können und den Umweg über forken und pull requests auszulassen. In Anbetracht des einfachen und überschaubaren Vokabulars erwies sich dieses Vorgehen als einfache und schnelle Lösung. Für komplexere Projekte ist es jedoch sicherlich nicht zu empfehlen. Die Sicherheit in Forks zu arbeiten, wäre hier zu bevorzugen, vor allem, wenn es um die Möglichkeiten funktionsrelevanter Änderungen geht. 
Grundlegend hat die Bearbeitung der Aufgabe positiv zur Auseinandersetzung mit Github und der Arbeit im Projekteam beigetragen.


## **3. Probleme bei der Publizierung des SkoHub-Vokabulars**

Nach einem ersten Transfer der Aufstellungssystematik des Lesesaals der USB Köln in unseren skohub-docker-vocabs-Fork gab es Probleme beim Aufbau der SkoHub Vocabs Static Website. Nach weiterer Auseinandersetzung mit Github konnten wir die Fehlermeldungen, die bei der Validierung durch den skohub-vocabs-docker entstanden waren, finden. Eine große Hilfe innerhalb der Fehlermeldungen war die Sektion "Node, where the error occured". Es handelte sich bei unseren Fehlern hauptsächlich um falsche Zeichensetzung, falsche Syntax oder fehlende Adressierungen wie bspw.:

 - URIS wurden in Anführungszeichen codiert
 - in "skos:hasTopConcept" ausgewiesene aber nicht erstellte Deskriptoren
 - in "prefLabel" nicht vergessene Großbuchstaben 

Diese Fehler produzierten einen kritischen "Violation Error" der das Vokabular an der Publizierung hinderte. Durch Korrektur aller Fehler und wiederholte Ausführung des Check-Skripts ließen sich alle Probleme identifizieren und beheben.


## **4. Verständnis vor und nach Bearbeitung RDF/SKOS**

Vor der Bearbeitung des Projektes gab es in der Gruppe keine oder nur wenige Kenntnisse über RDF/SKOS.
Grundlegende Informationen dazu wurden in der Lehrveranstaltung vermittelt, diese konnten durch Selbststudium gefestigt und erweitert werden.

Erst die Anwendung von RDF/Turtle/SKOS im Projekt allerdings führte zu einem ersten praktischen Verständnis, welches über das Grundverständnis hinausgeht. Zur Vollständigkeit dennoch zunächst Definitionen, auch um das gewonnene Grundverständnis wiederzugeben:

- RDF (Ressource Description Framwork): Datenmodell für Linked Open Data, jede Informartionseinheit besteht aus Triplen (Subjekt, Prädikat, Objekt)
- Entity-Relationship-Model
- RDF trifft Aussagen über Ressourcen
- eine mögliche Serialisierung von RDF: Turtle (Terse RDF Triple Language), eine menschenlesbare Darstellung von RDF-Graphen 
- SKOS (Simple Knowledge Organisation System): Ein Datenstandard (als Namensraum), um kontrollierte Vokabulare im Semantic Web zu veröffentlichen und diese nutz- und verknüpfbar zu machen

Über die Definitionen hinaus erwies sich vor allem die Lektüre zu SKOS in https://www.w3.org/TR/skos-reference/ als ergiebig, wenn es darum ging, das zu bearbeitetende Vokabular sinnvoll mit SKOS-Konzepten anzureichern.


## **5. Ausblick auf Nutzen und Anwendungsfälle**

Der unmittelbare und basale Nutzen des Projektes besteht darin, einen Teil der Aufstellungssystematik des Lesesaals in ein kontrolliertes und strukturiertes Vokabular übergeführt zu haben. Das neue SkoHub-Vokabular nutzt nun die Vorteile des Semantic Web und Linked Open Data. Zusätzlich wurde das Vokabular um englische Übersetzungen ergänzt.

Ein weiterer Vorteil ist die Ergänzung der Systematik um die SKOS-Konzepte "skos:altLabel" für eine vereinfachte Suche durch die Eingabe von Synonymen und bei der übergeordneten Hierarchiestufe "skos:exactMatch" bzw. "skos:broadMatch" um die Fachgebiete mit Wikidata zu verknüpfen.

Angesichts des anzunehmenden Rechercheverhaltens von Nutzer*innen sowie das Vorhandensein der Medien des Lesesaals der USB Köln im Sinne einer "Büchertapete" dürfte der praktische Nutzen gleichzeitig begrenzt sein.

Für uns als Bearbeitende ergibt sich in der sowohl mit Git als auch RDF/Turtle/SKOS gesammelten Erfahrung ein unmittelbarer Nutzen, der idealerweise im Weiterverfolgen von Fragen und Aufgaben in diesem Bereich besteht.

Durch eine zukünftige Übertragung der kompletten Aufstellungssystematik nach SKOS könnte die Nachnutzung erleichtert werden und eine einfachere Anbindung an normierte Vokabulare für zukünftige Zwecke ermöglicht werden.
