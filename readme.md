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

URL für Azure Hosting: https://carritiello-marko-lb324-cedwdda6ducvhdg5.switzerlandnorth-01.azurewebsites.net/

Damit das Einschreiben auf Azure funktioniert, muss ich Passwort manuell als Umgebungsvariable im Azure Portal eingetragen:

1. Im Azure Portal zum App Service navigieren.
2. Im linken Menü zu "Einstellungen" → "Umgebungsvariablen" gehen.
3. Im Reiter "App-Einstellungen" auf "+ Hinzufügen" klicken.
4. Name: `PASSWORD`, Wert: `Marko12234` (entspricht dem GitHub-Benutzernamen) eintragen.
5. Speichern klicken und App neustarten

Die App liest das Passwort danach zur Laufzeit über `os.getenv("PASSWORD")`, genau wie lokal über die `.env`-Datei.