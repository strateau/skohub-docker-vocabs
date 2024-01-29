Projektbericht


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
Eine spezifischere Form des Projektmanagements ("agil" etc.) wurde ausdrücklich nicht verfolgt.
Das Festlegen abgegrenzter Aufgaben gestaltete sich einfach, die überliegende Hierarchieebene und die beiden unterliegenden Ebenen wurden jeweils von einer Person bearbeitet.
Die Arbeiten in Github selbst - das Forken von Repos etc. - liefen als nicht definierte Aufgaben im Hintergrund und wurden im Laufe des Projekts von allen Gruppenmitgliedern wahrgenommen. Gangbarer Weg war schließlich, die Gruppenmitglieder in das Projekt einzuladen, um Änderungen direkt vornehmen zu können und den Umweg über forken und pull requests auszulassen. In Anbetracht des einfachen und überschaubaren Vokabulars erwies sich dieses Vorgehen als einfache und schnelle Lösung. Für komplexere Projekte ist es jedoch sicherlich nicht zu empfehlen. Die Sicherheit in Forks zu arbeiten, wäre hier zu bevorzugen, vor allem, wenn es um die Möglichkeiten funktionsrelevanter Änderungen geht. 
Grundlegend hat die Bearbeitung der Aufgabe positiv zur Auseinandersetzung mit Github und der Arbeit im Projekteam beigetragen.


## **3. Probleme beim Einrichten des Repos**

Nach einem ersten Transfer der Aufstellungssystematik des Lesesaals der USB Köln in unseren skohub-docker-vocabs-Fork gab es Probleme beim Aufbau der SkoHub Vocabs Static Website. Nach weiterer Auseinandersetzung mit Github konnten wir die Fehlermeldungen, die bei der Validierung durch den skohub-vocabs-docker entstanden waren, finden. Hier ließen sich die Fehlerquellen eindeutig identifizieren und die Fehler beheben. Eine große Hilfe innerhalb der Fehlermeldungen war die Sektion "Node, where the error occured". Es handelte sich bei unseren Fehlern hauptsächlich um falsche Zeichensetzung, falsche Syntax oder fehlende Adressierungen wie bspw.:

 - URIS in Anführungszeichen
 - in "skos:hasTopConcept" ausgewiesene aber nicht erstellte Deskriptoren
 - in "prefLabel" nicht vergessene Großbuchstaben 

Diese Fehler produzierten einen kritischen "Violation Error" der das Vokabular an der Publizierung hinderte.


## **4. Verständnis vor und nach Bearbeitung RDF/SKOS**

Vor der Bearbeitung des Projektes gab es in der Gruppe keine oder nur wenige Kenntnisse über RDF/SKOS.
Grundlegende Informationen dazu wurden in der Lehrveranstaltung vermittelt, diese konnten durch Selbststudium gefestigt und erweitert werden.
Erst die Anwendung von RDF/Turtle/SKOS im Projekt führte allerdings zu einem ansatzweise praktischen Verständnis, "wozu das Ganze gut ist", das
über die Definitionen hinausgeht. Der Vollständigkeit halber dennoch zuerst Definitionen, auch um das gewonnene Grundverständnis wiederzugeben:
- RDF (Ressource Description Framwork): Datenmodell für Linked Open Data, jede Informartionseinheit besteht aus Triplen (Subjekt, Prädikat, Objekt);
  Entity-Relationship-Model
- RDF trifft Aussagen über Ressourcen
- eine mögliche Serialisierung von RDF: Turtle (Terse RDF Triple Language) - menschenlesbare Darstellung von RDF-Graphen 
- SKOS (Simple Knowledge Organisation System): Datenstandard (als Namensraum), um kontrollierte Vokabulare im Semantic Web zu veröffentlichen, diese nutz- und verknüpfbar zu   machen
Über die Definitionen hinaus erwies sich vor allem die Lektüre zu SKOS in https://www.w3.org/TR/skos-reference/ als ergiebig, wenn es darum ging,
das bearbeitete Vokabular sinnvoll mit SKOS-Konzepten anzureichern.


## **5. Ausblick und Nutzen/Anwendungsfälle**

Der unmittelbare und basale Nutzen des Projektes besteht darin, die Darstellung der Systematik des Lesesaals in Englisch zu ermöglichen.
Zudem würde bei der Implementierung der Ergebnisse der Bearbeitung in SKOS für einzelne Systemstellen die Suche innerhalb der Systematik
mit broad matches und alt labels funktionieren. Ein gesuchter, aber nicht vorhandener Begriff führte somit immerhin zu einem inhaltlich trotzdem relevanten Suchergebnis.
Angesichts des anzunehmenden Rechercheverhaltens von Nutzer*innen sowie das Vorhandensein der Medien des Lesesaals der USB Köln im Sinne von "Büchertapete" dürfte
der praktische Nutzen gleichzeitig begrenzt sein.
Für uns als Bearbeitende ergibt sich in der sowohl mit Git als auch RDF/Turtle/SKOS gesammelten Erfahrung ein unmittelbarer Nutzen, der idealerweise im
Weiterverfolgen von Fragen und Aufgaben in diesem Bereich besteht.



Projekthistorie
- Zuerst suchten wir nach einer Systematik, die den Anforderungen der Aufgabe entsprechen könnte. Carlos Berbil stellte nach Rücksprache mit einem Mitarbeiter der USB Köln     zwei bereits in yml vorliegende Systematiken vor, die sich als geeignet erwiesen.
  - Wir entschieden uns für die manuelle Übertragung des Vokabulars, aus folgenden Gründen:
    - yml enthält wenig Informationen (nicht sehr interessante Datensätze)
    - man lernt Vorgänge
    - Der Versuch, die semi-automatisierte Übertragung von yml nach RDF zu verstehen und umzusetzen, ist nach einem mehrstündigen Versuch nicht gelungen.
      Das simple copy-pasten/Abtippen erwies sich im Rahmen des gewählten Vokabulars dagegen als schnelle und damit praktikable Lösung. Die Auswahl zusätzlichen,
      anreichernden normierten Vokabulars mittels altLabel, exactMatch usw. erforderte im Einzelfall ohnehin nötige manuelle Recherchearbeit.
   
- Auseinandersetzung mit SKOS
    - Welche Informationen sind sinnvoll zu überführen?
    - Welche Informationen lassen sich sinnvoll hinzufügen (Bsp. altLabel, exactMatch)
- Setup PURL
- Fork Repos aus Original - Skohub-Io
  - Carlos erstellte Hauptfork
- Auseinandersetzung mit Github
    - Pull Requests / Merge / Adminfunktionen / Auto-merge
    - Arbeit im Hauptfork
    - Arbeit im Nebenfork
- Erstellung Kanban Board
    - Aufteilung von Aufgaben
- Überführung der Felder aus "USBKöln".yml in SKOS per Hand
- 


Learnings
- update SKOS dauert einige Minuten
