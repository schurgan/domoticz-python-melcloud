# MELCloud Domoticz Plugin

Domoticz-Plugin zur Steuerung von Mitsubishi Klimaanlagen über **MELCloud**  
(getestet auf Raspberry Pi, stabiler Dauerbetrieb).

---
## Installation
1. Clone repository into your domoticz plugins folder
```
cd domoticz/plugins
git clone https://github.com/schurgan/domoticz-python-melcloud.git
```
2. Restart domoticz
3. Make sure that "Accept new Hardware Devices" is enabled in Domoticz settings
4. Go to "Hardware" page and add new item with type "MELCloud plugin"
## Plugin update

```
cd domoticz/plugins/domoticz-python-melcloud
git pull
```
## Features

- 🔐 Anmeldung über MELCloud (HTTPS)
- ❄️ Steuerung mehrerer Innengeräte
- 🔄 Automatische Gerätserkennung (Gebäude / Floors / Areas)
- 🎛️ Domoticz-Selectoren für:
  - Modus (Off, Warm, Cold, Vent, Dry, Auto)
  - Lüfterstufe
  - Soll-Temperatur
  - Horizontale & vertikale Lamellen
- 🌡️ Anzeige der Raumtemperatur
- 🕒 Anzeige des nächsten MELCloud-Updatezeitpunkts
- ⚡ (optional) Auslesen des gemeldeten Energieverbrauchs (ohne Anspruch auf Abrechnungsgenauigkeit)

---

## Technische Besonderheiten

- ✅ **JSON-SET API** (keine URL-encoded SETs mehr)
- ✅ **Rate-Limit für UNIT_INFO**, um MELCloud-HTTP-500 Fehler zu vermeiden
- ✅ Keine überlappenden Requests
- ✅ Saubere Typisierung (bool / int) für MELCloud
- ✅ Stabiler Betrieb bei kurzen Refresh-Intervallen
- ❌ Keine externen Abhängigkeiten

---

## Empfohlene Plugin-Einstellungen

- **Refresh Interval:** 2 Minuten  
- **Heartbeat:** intern 10 Sekunden
- **Debug:** None oder Basic (nur bei Problemen erhöhen)

---

## Changelog

### v1.0.0 (01.2026)
- Endversion, code Optimierung/Säuberung.

### v0.9.0 (12.2025)
- Stabile JSON-SET Implementierung
- UNIT_INFO Rate-Limit (verhindert HTTP 500)
- Korrekte Behandlung von Power / OperationMode Flags
- Verbesserte Initialisierung & Reconnect-Logik
- Aufgeräumter Code (Legacy-SET entfernt)
- Geeignet für Dauerbetrieb auf Raspberry Pi

### v0.8.0
- Heartbeat-Intervall konfigurierbar
- Sprachunterstützung erweitert

### v0.7.x
- Diverse Bugfixes
- Auto-Mode Fix
- Verbesserte HTTPS-Stabilität
- Synchronisation mit Original-Fernbedienung

---

## Hinweise

- Der gemeldete Energieverbrauch stammt direkt aus MELCloud und kann je nach Gerätekonfiguration variieren.
- Das Plugin ist für **Stabilität vor Aggressivität** ausgelegt (bewusstes Polling).

---

## Lizenz / Credits

Originalidee & Basis: **Gysmo**  
Weiterentwicklung & Stabilisierung: **schurgan / Dalonsic / ChatGPT**
