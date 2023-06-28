# Seminararbeit SS 2023 Michel Bauer 📖	🏈
## Die Struktur dieses Github-Repository basiert auf Kapitel 3 meiner Seminararbeit. Es zeigt die jeweiligen Schritte auf, die unternommen wurden, um den Datensatz zu generieren, eine explorative Datenanalyse durchzuführen, die Modelle zu testen, zu evaluieren und die Anwendbarkeit der Modelle aufzuzeigen.

### Da der finale Datensatz und das Modell TabNet zu groß sind wurden zwei Release getätigt
- Der erste Release beinhaltet den finalen Datensatz
- Der zweite Release die drei trainierten Modelle XGBoost, Random Forest und TabNet

### Notebook: Datensatz 💾
In diesem Notebook wird aufgezeigt, wie der Datensatz generiert wurde
- Zuerst wurde mit der ESPN-API ein play-by-play Datensatz generiert
- Mithilfe der ESPN- und der FiveThirtyEight-API die Elozahlen für die Teams generiert. Dabei wurden die Elozahlen genommen, die füraktuelle Saison und Woche aktuell waren
- Zuzästlich wurde mit Hilfe der ESPN-API die Zuschauerquote im Stadium extrahiert
- Anhand dieses Datnsatzes wurden weitere Features gebildet
    - Die verbleibende Zeit im Spiel
    - Der Punkteabstand zwischen den zwei Teams
    - Das aktuell führende Team
    - Und ein Feature, das anzeigt wie viele Scoring-Spielzüge das zurückliegende Team benötigt, um den Punktestand auszugleichen

### Notebook: EDA (Expolrative Daten Analyse) 📊
Hier werden verschiedene Grafiken generiert, die zum Verständnis der Daten beitragen:
- Eine Korrelationsmatrix: Sie zeigt die Korrelationen der Features untereinander an
- Ein Balken-Diagramm um zu visualisieren der Verteilung der Klassen im Datensatz
- Ein Balken-Diagramm, das aufzeigt in welchem Yardintervall die meisten Punkte erzielt werden
- Die Anderen Grafiken, die sich im Notebook verwendet, werden nicht für diese Arbeit verwendet

 ### Notebook: Training 🧠
 In diesem Notebook wird dargelegt, wie die einzelnen Modelle trainiert wurden. Dbei wird aufgezeigt, wie die Trainings-, Valdierungs-, und Trainingsdatensätze aufgeteilt wurden. Außerdem wird dargelegt, wie die einzelnen Preprocessingschritte umgesetzt wurden. Die Modelle wurden mit folgenden Methoden trainiert:
 - XGBoost: Early-Stopping-Methode
 - Random Forest: Da es keine Early-stopping Methode gab, wurde hierzu manuell die beste Baumgröße evaluiert und anschließend mit dieser Größe das Modell trainiert
 - TabNet: Early-Stopping-Methode

### Notebook: Evaluation 📈

