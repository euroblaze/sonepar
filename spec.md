# Softwareanforderungsspezifikation für die EDI-Integration von PowerOn™ mit Sonepar

## 1. Einführung

### 1.1 Zweck

Der Zweck dieses Dokuments besteht darin, die Anforderungen für die Integration der PowerOn™ ERP-Software mit der EDI-Schnittstelle von Sonepar zu definieren. Diese Integration ermöglicht es den Nutzern von PowerOn™, e-Procurement in ihre Betriebsprozesse zu einsetzen.

### 1.2 Referenzen

- [PowerOn™ Website](https://poweron.software)
- [Sonepar Website](https://sonepar.de)

## 2. Allgemeine Beschreibung

### 2.1 Produktübersicht

Die PowerOn™ Software wird an die Sonepar EDI-Schnittstelle angeschlossen. Produktinformationen werden über die OCI Open Catalog Interface von Sonepar bezogen und über die PDP-Schnittstelle in PowerOn™ eingebunden.

### 2.2 Schnittstellefunktionen

- **RFQs über EDI senden:** PowerOn™ sendet elektronische Anfragen an Sonepar über deren EDI.
- **Angebote erhalten:** PowerOn™ empfängt elektronische Angebote von Sonepar.
- **Kaufaufträge bestätigen:** Nutzer von PowerOn™ können die erhaltenen Angebote akzeptieren und Kaufaufträge bestätigen.
- **Auftragsbestätigungen erhalten:** Nach Eingang einer Bestellung bestätigt die EDI von Sonepar die Bestellung offiziell durch Ausgabe einer Auftragsbestätigung.
- **Versand und Lieferinformationen empfangen:** Sonepar bestätigt den Warenausgang an ihre Kunden durch elektronische Lieferscheine.
- **Rechnungen empfangen:** Nach der Lieferung der Waren werden die Rechnungen elektronisch an die Kunden von Sonepar (Unternehmen, die PowerOn™ nutzen) ausgestellt.

![image](https://github.com/euroblaze/sonepar/assets/7826363/37ba3324-fe69-4b54-ab10-bc5f92893032)

## 3. Spezifische Anforderungen

### 3.1 Funktionale Anforderungen

1. **Schnittstellenanforderungen:** Das System muss in der Lage sein, sich mit der EDI-Schnittstelle von Sonepar und der OCI-Schnittstelle zu verbinden.
2. **Datenanforderungen:** Das System muss in der Lage sein, Produktinformationen aus dem PDP von PowerOn™ abzurufen und zu nutzen.
3. **Prozessanforderungen:** Das System muss in der Lage sein, den gesamten E-Procurement-Prozess, von der Anfrage über die Bestätigung bis zur Rechnungsstellung, zu unterstützen.

### 3.2 Authentifizierungsanforderungen

1. **Authentifizierung zwischen PowerOn™ und Sonepar:** 

    Das System muss einen sicheren Authentifizierungsprozess implementieren, um die Kommunikation zwischen PowerOn™ und Sonepar zu ermöglichen. Dies wird durch folgende Schritte erreicht:

    - **Anforderung der Authentifizierung:** PowerOn™ sendet eine Authentifizierungsanforderung an Sonepar über eine sichere HTTPS-Verbindung. Diese Anforderung enthält die notwendigen Identifizierungsinformationen (z.B. API-Schlüssel oder andere Anmeldeinformationen).

    - **Bestätigung der Authentifizierung:** Sonepar prüft die Anmeldeinformationen und sendet eine Bestätigung zurück an PowerOn™, falls die Authentifizierung erfolgreich ist. Im Falle eines Fehlers sendet Sonepar eine Fehlermeldung zurück.

    - **Erhalt eines Authentifizierungstokens:** Nach erfolgreicher Authentifizierung stellt Sonepar ein Authentifizierungstoken aus, das für nachfolgende API-Aufrufe verwendet wird. 

    - **Verwendung des Tokens:** Bei nachfolgenden API-Aufrufen muss PowerOn™ dieses Token im HTTP Header (typischerweise als Bearer Token) senden, um seine Identität zu bestätigen und Zugriff auf die EDI-Schnittstelle zu erhalten.

Diese Authentifizierungsmethode stellt sicher, dass nur autorisierte Anfragen von PowerOn™ an Sonepar gesendet werden und umgekehrt, und dass alle Daten sicher übertragen werden. 


### 3.3 Nicht-Funktionale Anforderungen

1. **Leistung:** Das System muss in der Lage sein, eine große Menge von Produktinformationen zu verarbeiten und zeitnah zu reagieren.
2. **Sicherheit:** Alle übermittelten Daten müssen sicher und geschützt sein.
3. **Zuverlässigkeit:** Das System muss zuverlässig sein und eine hohe Verfügbarkeit aufweisen.
