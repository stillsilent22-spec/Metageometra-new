# Metageometra-new

Vorbereitung für einen automatischen Zenodo-Upload per GitHub Actions.

## PDF ablegen

Lege genau **eine** PDF-Datei in den Ordner `zenodo-upload/`.

Sobald eine PDF in diesem Ordner in das Repository gepusht wird, startet der Workflow `Upload PDF to Zenodo` und lädt die Datei in die konfigurierte Zenodo-Deposition hoch.

## Einmalig in GitHub konfigurieren

Vor dem ersten Upload müssen in den Repository-Einstellungen noch diese Werte gesetzt werden:

- Repository Secret `ZENODO_ACCESS_TOKEN`: persönlicher Zenodo-API-Token
- Repository Variable `ZENODO_DEPOSITION_ID`: ID der bestehenden Zenodo-Draft-Deposition
- Optional Repository Variable `ZENODO_API_URL`: Standard ist `https://zenodo.org/api`; für Sandbox `https://sandbox.zenodo.org/api`
- Optional Repository Variable `ZENODO_AUTO_PUBLISH`: auf `true` setzen, wenn die Deposition nach dem Upload automatisch veröffentlicht werden soll

## Ablauf

1. PDF in `zenodo-upload/` ablegen
2. Committen und in den Branch pushen
3. GitHub Actions lädt die PDF nach Zenodo hoch
4. Optional wird die Deposition automatisch veröffentlicht, wenn `ZENODO_AUTO_PUBLISH=true` gesetzt ist
