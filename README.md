# kinderflohmarkt_backend

# Willkommen auf unserer Plattform des Kinderflohmarktes-Standbuchung-WIP- #

Eine moderne, **webbasierte Plattform Eine moderne Web-Applikation zur Organisation von Kinderflohmärkten mit Fokus auf Tisch- und Standbuchungen**. Dieses Projekt befindet sich aktuell in der Entwicklung (Work in Progress).

Ein digitales Buchungssystem für Kinderflohmärkte löst ein echtes, praktisches Problem (jeder, der schon mal versucht hat, einen Tisch per Excel-Liste oder WhatsApp-Gruppe zu ergattern, weiß das zu schätzen).

​Da wir das Ganze als Mini-Agile-Simulation mit 3-wöchigen Sprints aufziehen, strukturieren wir das Projekt professionell. Für das Backend nutzen wir FastAPI (perfekt für Python, modern, blitzschnell und generiert die API-Dokumentation automatisch) zusammen mit SQLite als Datenbank für den einfachen Start.

​Viel spaß bei unserem 3 Wöchigen Sprint (21Tage)


Plann-Struktur:

# Woche 1: Fundament & Datenstruktur Tag 1: Projekt-Setup & Git-Initialisierung​Aufgabe: Erstelle die Ordnerstruktur, die .gitignore und die requirements.txt. Installiere die Bibliotheken.

**Tag 2:** Datenbank-Verbindung​Aufgabe: Schreibe die app/database.py mit der SQLite-Konfiguration und der get_db-Funktion.

**Tag 3:** Das Tisch-Modell (SQLAlchemy)​Aufgabe: Erstelle in app/models.py die Klasse Table mit Feldern für Tischnummer, Ort, Preis und Verfügbarkeit.

**Tag 4:** Das Buchungs-Modell (SQLAlchemy)​Aufgabe: Ergänze in app/models.py die Klasse Booking samt Fremdschlüssel (table_id) und Beziehungsdefinition (relationship).

**Tag 5:** Pydantic-Schemas für Tische​Aufgabe: Erstelle die Datei app/schemas.py und definiere TableBase, TableCreate und TableResponse.

**Tag 6:** Pydantic-Schemas für Buchungen​Aufgabe: Ergänze in app/schemas.py die Schemas BookingCreate und BookingResponse.

**Tag 7:** Wöchentlicher Code-Review & Docs-Check​Aufgabe: Erstelle eine minimale app/main.py, die nur die Tabellen in der Datenbank initialisiert und eine Root-Route {"message": "Hello"} hat. Teste, ob flohmarkt.db erstellt wird.

## Woche 2: CRUD-Logik & Tisch-API​Tag 8: Tisch-CRUD (Datenbank-Operationen)​Aufgabe: Erstelle die Datei app/crud.py und schreibe die Funktionen get_tables und create_table.


**Tag 9:** Tisch-API-Endpunkte​Aufgabe: Binde die Tisch-CRUD-Logik in app/main.py ein. Erstelle GET /tables/ und POST /tables/.

**Tag 10:** Manuelle Validierung im Browser​Aufgabe: Starte den Server (uvicorn app.main:app --reload), öffne /docs im Browser und lege manuell 3 Tische an. Behebung eventueller Tippfehler.

**Tag 11:** Buchungs-CRUD (Basis-Logik)​Aufgabe: Ergänze in app/crud.py die Funktion get_bookings und den Rumpf von create_booking.

**Tag 12:** Buchungs-Validierung & Logik (Das Herzstück)​Aufgabe: Programmiere in create_booking die Prüfung: Ist der Tisch frei? Wenn ja, berechne total_cost = table.price und setze den Tisch auf is_available = False.

**Tag 13:** Buchungs-API-Endpunkte​Aufgabe: Erstelle in app/main.py die Endpunkte GET /bookings/ und POST /bookings/.

**Tag 14:** Mid-Sprint Review & Refactoring​Aufgabe: Code aufräumen, ungenutzte Imports entfernen, Typen-Hinweise (Type Hints) in den Funktionen überprüfen.


### Woche 3: Stornierung, Automatisierte Tests & Dokumentation​Tag 15: Stornierungs-CRUD-Logik​Aufgabe: Schreibe in app/crud.py die Funktion delete_booking. Wichtig: Der verknüpfte Tisch muss wieder auf is_available = True gesetzt werden!

**Tag 16:** Stornierungs-API-Endpunkt​Aufgabe: Erstelle in app/main.py den Endpunkt DELETE /bookings/{booking_id}.

**Tag 17:** Test-Skript Setup​Aufgabe: Erstelle den Ordner scripts/ und die Datei test_api.py. Implementiere die requests-Logik, um automatisiert Test-Tische anzulegen.

**Tag 18:** Test-Skript Buchungssimulation​Aufgabe: Erweitere scripts/test_api.py, sodass ein Tisch gebucht und versucht wird, denselben Tisch noch einmal zu buchen (Erwartung: Fehlercode 400).

**Tag 19:** Test-Skript Stornierungssimulation​Aufgabe: Erweitere das Skript um den Test des DELETE-Endpunkts und prüfe, ob der Tisch danach wieder für Buchungen freigegeben ist.

**Tag 20:** Fehlerbehandlung & HTTP-Statuscodes verfeinern​Aufgabe: Gehe durch die Endpunkte und stelle sicher, dass bei Fehlern (z.B. Tisch nicht gefunden) die korrekten FastAPI HTTPException-Statuscodes (404 NOT FOUND, 400 BAD REQUEST) geworfen werden.

**Tag 21:** Sprint-Abschluss & Dokumentation​Aufgabe: Schreibe eine aussagekräftige README.md. Beschreibe, wie man die virtuelle Umgebung startet, die Abhängigkeiten installiert, die API startet und das Test-Skript ausführt.
