# LB 324

## Aufgabe 2
<!-- test ci workflow -->
Um die Automatisierungen zu aktivieren, muss man folgende Befehle einmalig nach dem Klonen des Repositories ausgeführen:

    pip install -r requirements.txt
    pre-commit install
    pre-commit install --hook-type pre-push

    
Danach läuft bei jedem `git commit` automatisch die Formatierung (`black`) und das Linting (`flake8`). Bei jedem `git push` werden zusätzlich die Tests (`pytest`) ausgeführt. Schlägt einer der Schritte fehl, wird der Commit bzw. Push abgebrochen, bis der Fehler behoben ist.

## Aufgabe 4
Erklären Sie hier, wie Sie das Passwort aus Ihrer lokalen `.env` auf Azure übertragen.