# Seminararbeit SS 2023 Michel Bauer 📖	🏈
## Die Struktur dieses Github-Repository basiert auf Kapitel 3 meiner Seminararbeit. Es zeigt die jeweiligen Schritte auf, die unternommen wurden, um den Datensatz zu generieren, eine explorative Datenanalyse durchzuführen, die Modelle zu testen, zu evaluieren und die Anwendbarkeit der Modelle aufzuzeigen.

### Da der endgültige Datensatz und das TabNet-Modell zu umfangreich sind, wurden zwei Releases erstellt.
- Der erste Release beinhaltet den finalen Datensatz
- Der zweite Release beinhaltet die drei trainierten Modelle XGBoost, Random Forest und TabNet

### Notebook: Datensatz 💾
Dieses Notebook zeigt, wie der Datensatz generiert wurde
- Zuerst wurde mit der ESPN-API ein Play-by-Play-Datensatz generiert
- Mit Hilfe den APIs von ESPN und FiveThirtyEight wurden die Elozahlen für die Teams generiert. Dabei wurden die aktuellen Elozahlen für die aktuelle Saison und Woche verwendet
- Zuzästlich wurde mit Hilfe der ESPN-API die Zuschauerquote im Stadium extrahiert
- Aus diesem Datensatz wurden weitere Merkmale gebildet
    - Die verbleibende Spielzeit
    - Der Punkteabstand zwischen den beiden Mannschaften
    - Das aktuell führende Team
    - Und ein Feature, das anzeigt, wie viele Scoring Plays das zurückliegende Team benötigt, um den Punktestand auszugleichen.

### Notebook: EDA (Expolrative Daten Analyse) 📊
Hier werden verschiedene Grafiken erzeugt, die zum Verständnis der Daten beitragen:
- Eine Korrelationsmatrix: Sie zeigt die Korrelationen zwischen den Merkmalen
- Ein Balkendiagramm, um die Verteilung der Klassen im Datensatz zu visualisieren
- Ein Balkendiagramm, das zeigt, in welchem Yard-Intervall die meisten Punkte erzielt werden
- Die anderen Diagramme im Notebook werden für diese Arbeit nicht verwendet.

 ### Notebook: Training 🧠
 In diesem Notebook wird dargelegt, wie die einzelnen Modelle trainiert wurden.  Es wird gezeigt, wie die Trainings-, Validierungs- und Trainingsdatensätze aufgeteilt wurden.  Darüber hinaus wird beschrieben, wie die  Preprocessingschritte durchgeführt wurden. Die Modelle wurden mit den folgenden Methoden trainiert:
 - XGBoost: Early-Stopping-Methode
 - Random Forest: Da es keine Early-stopping Methode gab, wurde hierzu manuell die beste Baumgröße evaluiert und anschließend mit dieser Größe das Modell trainiert
 - TabNet: Early-Stopping-Methode

### Notebook: Evaluation 📈
Dieses Notebook zeigt, wie die Accuracy für den gesamten Datensatz berechnet wird und wie die Diagramme erzeugt werden, die zeigen, wie sich die einzelnen Modelle in bestimmten Zeitintervallen verhalten. Im nächsten Schritt wird der Datensatz nach bestimmten Kriterien gefiltert:
- Es werden nur Spielzüge betrachtet, bei denen es gerade Unentschieden zwischen den Teams steht
- Spielzüge, bei denen das zurückliegende Team mindestens ein Scoring-Play benötigt, um den Spielstand auszugleichen
- Spielzüge, in denen das zurückliegende Team mindestens zwei Scoring Plays benötigt, um den Spielstand auszugleichen.
Anschließend wurde das gleiche Verfahren wie für den gesamten Datensatz angewendet.

### Notebook: Anwendung 🔨
Abschließend werden einzelne Spiele und Saisons genauer betrachtet. Dazu wurde das Spiel Detroit Lions vs. Cincinnati Bengals (Saison 2022, Woche 10) mit dem Modell XGBoost genauer analysiert. Folgende Schritte wurden durchgeführt:
- Zunächst wurde der Verlauf der Gewinnwahrscheinlichkeiten der beiden Mannschaften visualisiert
- Anschließend wurden die Plays extrahiert und analysiert, die für die Veränderung der Gewinnwahrscheinlichkeit verantwortlich waren

Im letzten Teil des Notebooks wurde das beste Passing Play (ohne Passing Touchdowns) der Saison 2022 ermittelt. Dazu wurden alle Passing Plays der Saison gefiltert und das Play mit dem größten Einfluss auf die Gewinnwahrscheinlichkeit ausgewählt.
 

