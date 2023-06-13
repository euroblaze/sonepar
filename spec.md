# Softwareanforderungsspezifikation für die EDI-Integration von PowerOn™ mit Sonepar

## 1. Einführung

### 1.1 Zweck

Der Zweck dieses Dokuments besteht darin, die Anforderungen für die Integration der PowerOn™ ERP-Software mit der EDI-Schnittstelle von Sonepar zu definieren. Diese Integration ermöglicht es den Nutzern von PowerOn™, e-Procurement-Prozesse zu nutzen.

### 1.2 Referenzen

- [PowerOn™ Website](https://poweron.software)
- [Sonepar Website](https://sonepar.de)

## 2. Allgemeine Beschreibung

### 2.1 Produktübersicht

Die PowerOn™ Software wird an die Sonepar EDI-Schnittstelle angeschlossen. Produktinformationen werden über die OCI Open Catalog Interface von Sonepar bezogen und über die PDP-Schnittstelle in PowerOn™ eingebunden.

### 2.2 Produktfunktionen

- **RFQs über EDI senden:** PowerOn™ sendet elektronische Anfragen an Sonepar über deren EDI.
- **Angebote erhalten:** PowerOn™ empfängt elektronische Angebote von Sonepar.
- **Kaufaufträge bestätigen:** Nutzer von PowerOn™ können die erhaltenen Angebote akzeptieren und Kaufaufträge bestätigen.
- **Auftragsbestätigungen erhalten:** Nach Eingang einer Bestellung bestätigt die EDI von Sonepar die Bestellung offiziell durch Ausgabe einer Auftragsbestätigung.
- **Versand und Lieferinformationen empfangen:** Sonepar bestätigt den Warenausgang an ihre Kunden durch elektronische Lieferscheine.
- **Rechnungen empfangen:** Nach der Lieferung der Waren werden die Rechnungen elektronisch an die Kunden von Sonepar (Unternehmen, die PowerOn™ nutzen) ausgestellt.

## 3. Spezifische Anforderungen

### 3.1 Funktionale Anforderungen

1. **Schnittstellenanforderungen:** Das System muss in der Lage sein, sich mit der EDI-Schnittstelle von Sonepar und der OCI-Schnittstelle zu verbinden.
2. **Datenanforderungen:** Das System muss in der Lage sein, Produktinformationen aus dem PDP von PowerOn™ abzurufen und zu nutzen.
3. **Prozessanforderungen:** Das System muss in der Lage sein, den gesamten E-Procurement-Prozess, von der Anfrage über die Bestätigung bis zur Rechnungsstellung, zu unterstützen.

### 3.2 Nicht-Funktionale Anforderungen

1. **Leistung:** Das System muss in der Lage sein, eine große Menge von Produktinformationen zu verarbeiten und zeitnah zu reagieren.
2. **Sicherheit:** Alle übermittelten Daten müssen sicher und geschützt sein.
3. **Zuverlässigkeit:** Das System muss zuverlässig sein und eine hohe Verfügbarkeit aufweisen.
