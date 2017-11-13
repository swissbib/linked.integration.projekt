


***13.11.2017 (Christoph / Günter)***

- momentaner task Christoph: Knowledge Card - Personen
- Überlegungen: wie mit dem JavaScript Code von Chur umgehen?
- konkret: wie wird die Information abgerufen, ob zu einer Person weitergehende Daten vorliegen oder nicht?
- Alternativen:


a) Typescript 

- Verbesserung der Codequalität und bessere Testbarkeit
- Logik (Abruf und Auswertung der Information weiterhin auf der Clientseite - wie jetzt schon bei Chur)
- Nachteil: für swissbib neue Technologie - bisher so nicht verwendet

b) die komplette Knowledgecard wird auf der Serverseite zusammengestellt (PHP Code)


- Nachteil: kann langsam sein (zumindest verzögerter Aufbau)

c) anstelle von Elasticsearch verwenden wir SOLR, bedeutet Wegfall von SOLR)


Diskussion 

gemeinsame Gedanken Cristoph / Günter:

* Codequalität und Testbarkeit und damit vertretbarer Aufwand der Wartung in der Zukunft ist wichtig

Hinweise Günter

* Wegfall von Elasticsearch ist für mich keine Option. Wir haben uns bewusst für ES im Rahmen von linked.swissbib.ch entschieden.
* In Zukunft gehe ich davon aus, dass sich eine Discovery-Präsentationskomponente immer mehr aus verschiedenen Datentöpfen wird bedienen müssen. Deshalb wird der Mechanismus gebraucht
* typisiertes JavaScript ist der aktuelle Gang der Dinge. Dem wird sich swissbib nicht verschliessen (können). Mit der Konsequenz: das wir uns das Wissen aneigenen werden.


von beiden getragene Entscheidung (Günter / Christoph)

* Der Weg von Chur (Logik als JavaScript Client code) wird nicht grundsätzlich verlassen. Wir setzen hierfür jedoch TypeScript ein.

    


