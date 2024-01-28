Projektbericht

1. Aufgabenstellung

2. Herangehensweise
3. 
4. Probleme
   - Fehlermeldungen aufgrund von falscher Zeichensetzungen, Syntax und Adressierungen
         - bspw. URIS in Anführungszeichen
         - bspw. oben ausgewiesene aber nicht erstellte "Klassen" (?)
         - bspw. Großbuchstaben nicht vergeben bei "prefLabel"
   - Debugging per skos validator per Github Checks


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
