# Big_Data_Project

Dies ist das Repository zu dem Big-Data-Projekt von Insa Belter, Neelis Rüter und Noah Wagner.

Im Rahmen des Projektes wird die Abhängigkeit zwischen Fußgängerzahlen in ausgewählten Straßen
deutscher Großstädte mit Wettereinflüssen und der Pandemieentwicklung im Jahr 2020 untersucht.

Um die Notebooks ausführen zu können, sollte folgende Reihenfolge betrachtet werden:

(Befehlssatz für Windows:)
1. MongoDB installieren
2. Kafka installieren
3. Kafka zookeeper und Server starten: \
	.\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties \
	.\bin\windows\kafka-server-start.bat .\config\server.properties 
4. Topics mittels folgender Befehle erstellen: \
	.\bin\windows\kafka-topics.bat --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic pedestrians \
	.\bin\windows\kafka-topics.bat --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic incidences
5. Mittels der Jupyter Notebooks "Kafka Consumer" und "Kafka Producer" die MongoDB mit den beigelegten CSV-Daten füllen \
	(Alternativ manuelles Einpflegen der CSV-Daten in die MongoDB)
6. Notebook "Analyse und Visualisierung" ausführen, um die Ergebnisse zu betrachten