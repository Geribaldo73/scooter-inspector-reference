# Scooter Inspector – Referenzdatenbank

Versionierte Referenzdaten für die Android-App **Scooter Inspector** (technische Prüfung von E-Scootern).

Die App ruft ausschließlich diese Datei per HTTPS-GET ab:

```
https://raw.githubusercontent.com/Geribaldo73/scooter-inspector-reference/main/reference_db.json
```

Dabei werden keine Bluetooth-Kennungen, Fotos oder Prüfberichte übertragen.

## Regeln für Änderungen

- Vor jeder Veröffentlichung `dataVersionCode` erhöhen (Format `JJJJMMTTNN`). Ältere oder gleiche Versionen lehnt die App ab.
- `dataVersion` (lesbar) passend anpassen.
- Technische Werte nur mit `"status": "VERIFIED"` **und** mindestens einer Quelle in `sources` eintragen.
- Unbekannte Werte weglassen bzw. `"status": "UNKNOWN"` ohne Wert. Keine geschätzten oder erfundenen Daten.
- Jede exakte Modellvariante als eigener Datensatz – ungeprüfte Varianten nicht zusammenführen.
- Fundstellen von Kennzeichnungen (`markings`) nur mit Quelle, Zitat (`sourceQuote`) und `verifiedAt` als `CONFIRMED`.
- Keine Demo-Daten (`isDemo`, `DEMO`) in dieser Datei.

Die App validiert jede Datei vor der Übernahme (Schema, Quellen, Plausibilität, Version). Ungültige Updates werden
verworfen, die bisherigen Daten bleiben aktiv. Das vollständige Schema beschreibt `ARCHITECTURE.md` im App-Projekt.

## Quellen

Alle Quellen stehen in der Datei unter `sources` (u. a. Bluetooth SIG Assigned Numbers, Herstellerseiten).
