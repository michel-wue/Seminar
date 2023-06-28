# Seminararbeit SS 2023 Michel Bauer
## Die Struktur dieses Github-Repository basiert auf Kapitel 3 meiner Seminararbeit. Es zeigt die jeweiligen Schritte auf, die unternommen wurden, um den Datensatz zu generieren, eine explorative Datenanalyse durchzuführen, die Modelle zu testen, zu evaluieren und die Anwendbarkeit der Modelle aufzuzeigen.

### Da der finale Datensatz und das Modell TabNet zu groß sind wurden zwei Release getätigt
- Der erste Release beinhaltet den finalen Datensatz
- Der zweite Release die drei trainierten Modelle XGBoost, Random Forest und TabNet

### Notebook: Datensatz
In diesem Notebook wird aufgezeigt, wie der Datensatz generiert wurde
- Zuerst wurde mit der ESPN-API ein play-by-play Datensatz generiert
- Mithilfe der ESPN- und der FiveThirtyEight-API die Elozahlen für die Teams generiert. Dabei wurden die Elozahlen genommen, die füraktuelle Saison und Woche aktuell waren
- Zuzästlich wurde mit Hilfe der ESPN-API die Zuschauerquote im Stadium extrahiert
- Anhand dieses Datnsatzes wurden weitere Features gebildet
    - Die verbleibende Zeit im Spiel
    - Der Punkteabstand zwischen den zwei Teams
    - Das aktuell führende Team
    - Und ein Feature dasanzeigt wie viele Scoring-Spielzüge 
